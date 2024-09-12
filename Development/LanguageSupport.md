# Language Support

## Frontend

ZBook currently supports Simplified Chinese and English. To add support for new languages to the frontend of ZBook, follow these steps:

### 1. Add Language Files

Create a new language file in the `zbook_frontend/messages` directory, such as `fr.json`, and add the corresponding translation content. For example:

```json
{
  "welcome": "Bienvenue",
  "login": "Se connecter",
  "register": "S'inscrire",
  "dashboard": "Tableau de bord"
}
```

Ensure that you provide translation content for each field that needs to be translated.

### 2. Update Language Configuration

In the `zbook_frontend/src/navigation.ts` file, add the new language to the `locales` configuration. For example, to add French support:

```typescript
import frMessages from "../messages/fr.json";

// Add the new language to the locales object
const locales = {
  en: enMessages,
  zh: zhMessages,
  fr: frMessages, // Add new language
};
```

### 3. Update Global Type Definitions

In the `zbook_frontend/global.d.ts` file, add type declarations for the new language. You might need to update interfaces or type definitions to include the new language. For example:

```typescript
declare module "i18n" {
  type Locale = "en" | "zh" | "fr"; // Add new language type
}
```

### 4. Navbar Language Switching

To implement language switching in the `navbar`, update the corresponding component to support selecting languages from `localeMap`. If you have a `Navbar` component, update the `zbook_frontend/src/components/navbars/NavLang.tsx` file with the `localeMap`:

```typescript
const localeMap = {
  en: "English",
  zh: "简体中文",
  de: "Deutsch",
  fr: "Français",
  es: "Español",
  jp: "日本語",
  ko: "한국어", // Add new languages
};
```

### 5. Testing

After completing the above steps, test the changes by navigating to the `zbook_frontend` directory, running `npm run lint` and `npm run build`. If there are no errors, you can start the local server and check the results.

## Backend

After updating the frontend, some modifications are also needed on the backend. First, add the new language in the `zbook_backend/util/lang.go` file:

```go
const (
    LangZh = "zh"
    LangEn = "en"
    LangDe = "de" // Add new language
)
```

Next, update the `ValidateLang` function in the `zbook_backend/val/validator.go` file to include the new language:

```go
func ValidateLang(value string) error {
    if value != util.LangEn && value != util.LangZh && value != util.LangDe {
      return fmt.Errorf("invalid language")
    }
    return nil
}
```

!!! info Completed
    After completing the above frontend and backend changes, ZBook will support the new language!

## Database

The dashboard can support geographic information in multiple languages, which is somewhat decoupled from the frontend. If the backend does not have corresponding language database information, it will return default language `en` information, as shown in the image below:

![lang_support](../开发/assets/lang_support.gif)

If you want the visitor information in the image above to support your language version, additional modifications are needed.

### 1. Multilingual City Names

```go
type GeoData struct {
    IPRangeCIDR  string
    CityNameEn   *string
    CityNameZhCn *string
    Latitude     *float64
    Longitude    *float64
}

type CityNames struct {
    En   *string `maxminddb:"en"`
    ZhCN *string `maxminddb:"zh-CN"`
}
```

### 2. Retrieve City Name

```go
func getCityName(record *util.GeoInfo, lang string) string {
    switch lang {
    case "en":
      return record.CityNameEn
    case "zh_cn":
      return record.CityNameZhCn
    default:
      return record.CityNameEn
    }
}
```

### 3. Add New Column to Database

```sql
-- Add a new column city_name_de
ALTER TABLE "geoip" ADD COLUMN city_name_de TEXT;
```

### 4. Data Conversion

!!! warning TODO
    To be continued
