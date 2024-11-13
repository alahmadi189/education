### JSON Structure for Translation Keys

This JSON includes keys for English and Arabic translations organized for the `head`, `body`, and `main` elements.

```json
{
  "en": {
    "title": "Study in China - Unique Opportunity",
    "header": {
      "chineseSymbol": "China",
      "gatewayTitle": "Your Gateway to China"
    },
    "body": {
      "subtitle": "🌏 Open to All Nationalities",
      "highlightTitle": "🎓 Unique Educational Opportunity",
      "highlightDescription": "Study at your chosen Chinese university! Experience the rich culture and unlock your future potential.",
      "registrationFee": "Registration Fee: Only 1,500 SAR",
      "benefits": {
        "universityChoiceTitle": "🏛️ University Choice",
        "universityChoiceDescription": "Freedom to select your preferred Chinese university",
        "languageMasteryTitle": "🗣️ Language Mastery",
        "languageMasteryDescription": "Comprehensive Chinese language program",
        "culturalImmersionTitle": "🏛️ Cultural Immersion",
        "culturalImmersionDescription": "Experience authentic Chinese culture firsthand",
        "careerAdvantageTitle": "🎯 Career Advantage",
        "careerAdvantageDescription": "Gain a competitive edge in the global market"
      },
      "contactSection": {
        "contactTitle": "Secure Your Spot Now!",
        "contactDescription": "Don't miss this life-changing opportunity",
        "whatsappButton": "WhatsApp: +966 537394467",
        "wechatButton": "WeChat ID: alahmadi819"
      }
    }
  },
  "ar": {
    "title": "الدراسة في الصين - فرصة فريدة",
    "header": {
      "chineseSymbol": "الصين",
      "gatewayTitle": "بوابتك إلى الصين"
    },
    "body": {
      "subtitle": "🌏 مفتوحة لجميع الجنسيات",
      "highlightTitle": "🎓 فرصة تعليمية فريدة",
      "highlightDescription": "ادرس في الجامعة الصينية التي تختارها! استمتع بالثقافة الغنية وافتح آفاق مستقبلك.",
      "registrationFee": "رسوم التسجيل: ١٥٠٠ ريال سعودي فقط",
      "benefits": {
        "universityChoiceTitle": "🏛️ اختيار الجامعة",
        "universityChoiceDescription": "حرية اختيار الجامعة الصينية التي تفضلها",
        "languageMasteryTitle": "🗣️ إتقان اللغة",
        "languageMasteryDescription": "برنامج شامل للغة الصينية",
        "culturalImmersionTitle": "🏛️ انغماس ثقافي",
        "culturalImmersionDescription": "تجربة الثقافة الصينية الأصيلة بشكل مباشر",
        "careerAdvantageTitle": "🎯 ميزة مهنية",
        "careerAdvantageDescription": "احصل على ميزة تنافسية في السوق العالمية"
      },
      "contactSection": {
        "contactTitle": "احجز مكانك الآن!",
        "contactDescription": "لا تفوت هذه الفرصة التي تغير الحياة",
        "whatsappButton": "واتساب: +966 537394467",
        "wechatButton": "معرف WeChat: alahmadi819"
      }
    }
  }
}
```

### JavaScript Code for Language Toggle

Below is JavaScript code to dynamically update the page content based on the user's preferred language.

```javascript
// Define the translations object
const translations = {
    en: { /* Translation data for English from the JSON above */ },
    ar: { /* Translation data for Arabic from the JSON above */ }
};

// Function to change language
function setLanguage(lang) {
    const content = translations[lang];

    // Update title
    document.title = content.title;

    // Update header
    document.querySelector('.chinese-symbol').textContent = content.header.chineseSymbol;
    document.querySelector('.header-content h1').textContent = content.header.gatewayTitle;

    // Update body content
    document.getElementById('subtitle').textContent = content.body.subtitle;
    document.querySelector('.highlight-box h2').textContent = content.body.highlightTitle;
    document.querySelector('.highlight-box p').textContent = content.body.highlightDescription;
    document.querySelector('.price-tag').textContent = content.body.registrationFee;

    // Update benefits
    const benefits = document.querySelectorAll('.benefit-item');
    const benefitKeys = content.body.benefits;
    benefits[0].querySelector('h3').textContent = benefitKeys.universityChoiceTitle;
    benefits[0].querySelector('p').textContent = benefitKeys.universityChoiceDescription;
    benefits[1].querySelector('h3').textContent = benefitKeys.languageMasteryTitle;
    benefits[1].querySelector('p').textContent = benefitKeys.languageMasteryDescription;
    benefits[2].querySelector('h3').textContent = benefitKeys.culturalImmersionTitle;
    benefits[2].querySelector('p').textContent = benefitKeys.culturalImmersionDescription;
    benefits[3].querySelector('h3').textContent = benefitKeys.careerAdvantageTitle;
    benefits[3].querySelector('p').textContent = benefitKeys.careerAdvantageDescription;

    // Update contact section
    document.querySelector('.contact-section h2').textContent = content.body.contactSection.contactTitle;
    document.querySelector('.contact-section p').textContent = content.body.contactSection.contactDescription;
    document.querySelectorAll('.contact-button')[0].textContent = content.body.contactSection.whatsappButton;
    document.querySelectorAll('.contact-button')[1].textContent = content.body.contactSection.wechatButton;
}

// Event listener for language selection
document.getElementById('languageSelect').addEventListener('change', (event) => {
    setLanguage(event.target.value);
});
```

### HTML Select Element for Language Toggle

Add this `<select>` dropdown in the HTML body to allow users to choose a language.

```html
<select id="languageSelect">
    <option value="en">English</option>
    <option value="ar">العربية</option>
</select>
```

This setup will update all specified elements when the user changes their language preference, using the keys in the JSON object to translate and display content in English or Arabic.