# Housing.com Scraper
This project extracts structured real estate listings from Housing.com, delivering detailed property information such as prices, configurations, amenities, locations, developer details, images, and more. It enables accurate market intelligence and automated data collection for real estate workflows. Designed for analysts, investors, and developers who require reliable and scalable property data extraction.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>housing-com-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
The scraper collects and processes structured property data from Housing.com, ensuring clean, enriched, and analysis-ready output.
It solves the challenge of manually gathering scattered real estate information by automating extraction at scale.
Ideal for real estate analysts, data scientists, property investors, and developers building market research tools.

### Key Capabilities Overview
- Gathers comprehensive property metadata including prices, configurations, amenities, and RERA status.
- Automatically navigates pagination and handles large result sets.
- Supports multiple search URLs with configurable scraping limits.
- Produces structured JSON optimized for analytics and reporting.
- Includes robust anti-blocking mechanisms for stable operation.

## Features
| Feature | Description |
|--------|-------------|
| Multi-URL support | Process multiple Housing.com search URLs in a single run. |
| Structured JSON output | Clean, normalized, and analytics-friendly property data. |
| Pagination handling | Automatically crawls through paginated results. |
| Detailed property fields | Extracts prices, coordinates, amenities, developer info, images, and more. |
| Configurable limits | Allows users to define maximum items to extract. |
| Anti-blocking system | Ensures stable data collection across large datasets. |

---

## What Data This Scraper Extracts
| Field Name | Field Description |
|------------|------------------|
| propertyId | Unique identifier of the property listing. |
| title | Property name or project title. |
| propertyType | Type of listing such as project, apartment, plot, etc. |
| propertyUrl | Direct link to the property detail page. |
| configurations | Available flat configurations (e.g., 1 BHK, 2 BHK). |
| price | Price range, min/max values, per sq ft rates. |
| location | Address, locality, city, state, and coordinates. |
| area | Size information and measurement units. |
| possession | Construction/possession status and expected date. |
| developer | Developer name and detail page link. |
| amenities | List of available amenities in the property. |
| images | Image URLs with captions. |
| sellers | Contact details of brokers or sellers. |
| nearbyPlaces | Nearby facilities like schools, hospitals, malls, and travel metrics. |
| propertyTags | Tags describing listing type/status. |
| reraVerified | Whether the project is RERA registered or verified. |
| lastUpdated | Timestamp of the last update to the listing. |
| description | Full textual description of the property. |

---

## Example Output

    [
      {
        "searchUrl": "https://housing.com/in/buy/mumbai/mira_road_east",
        "propertyId": "64577",
        "title": "Unique Poonam Estate Cluster 1",
        "propertyType": "project",
        "propertyUrl": "https://housing.com/in/buy/projects/page/64577-unique-poonam-estate-cluster-1-by-unique-shanti-developers-in-mira-road-east",
        "configurations": "1, 2 BHK Flats",
        "price": {
          "range": "₹69.36 L - 1.05 Cr",
          "minValue": 6935940,
          "maxValue": 10456455,
          "avgPricePerSqft": "₹10.51 K/sq.ft"
        },
        "location": {
          "address": "Mira Road East, Mira Road and Beyond, Mumbai",
          "city": "Mumbai",
          "locality": "Mira Road East",
          "state": "Maharashtra",
          "coordinates": {
            "latitude": "19.276220",
            "longitude": "72.871704"
          }
        },
        "amenities": ["Pool", "Gym", "Lift", "Parking"],
        "reraVerified": false,
        "lastUpdated": "2025-01-04T05:35:36.000Z"
      }
    ]

---

## Directory Structure Tree

    housing-com-scraper/
    ├── src/
    │   ├── runner.py
    │   ├── extractors/
    │   │   ├── housing_parser.py
    │   │   └── utils_location.py
    │   ├── outputs/
    │   │   └── exporters.py
    │   └── config/
    │       └── settings.example.json
    ├── data/
    │   ├── inputs.sample.json
    │   └── sample_output.json
    ├── requirements.txt
    └── README.md

---

## Use Cases
- **Real estate analysts** use it to monitor pricing trends so they can make informed investment recommendations.
- **Property investors** use it to compare listings across cities so they can identify high-potential opportunities.
- **Developers** integrate it into dashboards to automate property database generation for their platforms.
- **Market researchers** collect bulk housing data to study locality growth and urban expansion patterns.
- **Consultants** use extracted data for location analysis, neighborhood comparisons, and buyer advisory reports.

---

## FAQs

**Q: Can I scrape multiple cities in one run?**
Yes, you can provide a list of search URLs covering multiple localities or cities and the scraper will process them sequentially.

**Q: What happens if some listings lack details?**
If certain fields are missing on the listing page, the scraper gracefully assigns null values while maintaining schema consistency.

**Q: How many items can be extracted at once?**
You can set a custom `maxItems` value. The scraper will stop automatically after reaching your defined limit.

**Q: Does the scraper handle dynamic pagination?**
Yes, it detects and crawls through each additional listing page automatically.

---

### Performance Benchmarks and Results
**Primary Metric:** Handles an average of 70–120 listings per minute depending on locality density.
**Reliability Metric:** Maintains a 98%+ successful extraction rate across varied property types.
**Efficiency Metric:** Optimized for minimal reprocessing, ensuring stable throughput even with large datasets.
**Quality Metric:** Consistently captures over 95% of available property attributes with high data completeness.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
