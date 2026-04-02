# 🌍 GCC Open Geospatial Database
**أكبر قاعدة بيانات جغرافية مفتوحة ومصنفة لدول الخليج العربي**

![Data Format](https://img.shields.io/badge/Format-GeoJSON-blue)
![Coverage](https://img.shields.io/badge/Coverage-GCC_Countries-green)
![OpenStreetMap](https://img.shields.io/badge/Source-OpenStreetMap-7ebd42)
![Data Date](https://img.shields.io/badge/Data_Date-March_31,_2026-orange)

## 📖 Overview | نبذة عن المشروع
Finding clean, categorized, and free geospatial data (GIS) for the Gulf Cooperation Council (GCC) countries is a huge challenge for Data Scientists, Analysts, and Developers. 

This repository provides **ready-to-use, highly structured GeoJSON files** extracted from OpenStreetMap (OSM). The raw data has been heavily processed, cleaned, and spatially split into individual GCC countries (Saudi Arabia, UAE, Qatar, Kuwait, Bahrain, Oman) to save you hundreds of hours of data engineering.

**📅 Data Vintage:** All data in this repository is extracted and up to date as of **March 31, 2026**.

يهدف هذا المشروع إلى توفير بيانات جغرافية نظيفة ومجانية ومقسمة باحترافية لدول الخليج بصيغة GeoJSON جاهزة للاستخدام الفوري في تحليل البيانات (Python, R)، وتطوير التطبيقات، وأنظمة الـ GIS (QGIS, ArcGIS)، وبرامج ذكاء الأعمال (PowerBI, Tableau).

**📅 تاريخ البيانات:** جميع البيانات المرفوعة في هذا المستودع محدثة حتى تاريخ **31 مارس 2026**.

---

## ✨ Why Use This Database? | مميزات البيانات
- **Ready to Use:** No need to deal with complex `.pbf` files or heavy XML parsing. Just download the `.geojson` and start analyzing.
- **Bilingual Support:** Prioritizes Arabic names (`name:ar`) when available, making it perfect for local applications.
- **Smart Categorization:** Millions of raw OSM points and polygons have been neatly grouped into 7 logical categories.
- **Accurate Boundaries:** Features are spatially joined and strictly clipped to the official administrative boundaries of each country.

---

## 📂 Data Structure | هيكلة البيانات
The data is organized by country. Inside each country's folder, you will find 7 main files (Note: Large files might be compressed as `.zip`):

```text
GCC_Geospatial_Database/
├── 🇸🇦 Saudi_Arabia/
│   ├── 1_Boundaries_Regions.geojson
│   ├── 1_Boundaries_Governorates.geojson
│   ├── 2_Amenities_Points.geojson
│   ├── 3_Shops_Polygons.geojson
│   ├── 5_Buildings.geojson.zip
│   └── 7_Highways_Roads.geojson.zip
├── 🇦🇪 UAE/
├── 🇶🇦 Qatar/
├── 🇰🇼 Kuwait/
├── 🇧🇭 Bahrain/
└── 🇴🇲 Oman/
```

---

## 🗺️ Available Categories | التصنيفات المتاحة
1. **Boundaries (الحدود الإدارية):** Regions (Level 4), Governorates (Level 6), Districts/Neighborhoods (Level 8-11).
2. **Amenities & POIs (الخدمات والمرافق):** Schools, Hospitals, Mosques, Banks, Cafes, Restaurants, etc.
3. **Shops & Commercial (المحلات التجارية):** Supermarkets, Malls, Bakeries, Pharmacies.
4. **Leisure & Tourism (الترفيه والسياحة):** Parks, Museums, Hotels, Stadiums.
5. **Buildings (المباني):** Polygons for residential, commercial, and industrial buildings.
6. **Landuse & Nature (استخدامات الأراضي):** Industrial zones, Forests, Beaches, Residential areas.
7. **Highways & Roads (شبكات الطرق):** Motorways, Trunks, Primary roads, etc.

---

## 💻 How to Use | طريقة الاستخدام

You can easily load these files into your favorite tools:

### Python (GeoPandas)
```python
import geopandas as gpd

# Load Saudi Arabia Amenities (Hospitals, Schools, etc.)
gdf = gpd.read_file("Saudi_Arabia/2_Amenities_Points.geojson")

# Filter only Hospitals
hospitals = gdf[gdf['amenity'] == 'hospital']
print(hospitals.head())
```

### Other Tools:
- **QGIS / ArcGIS:** Simply drag and drop the `.geojson` files into the software.
- **PowerBI:** Convert to TopoJSON or use the native map visuals to plot the data.
- **Web Apps (Leaflet / Mapbox):** Fetch the GeoJSON directly via API or local import.

---

## 📧 Custom Data Requests | طلبات البيانات الخاصة
Do you need a specific dataset? (e.g., "Only Pharmacies in Riyadh" or "Merge all GCC Roads into one file"). 
Feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/YOUR_LINKEDIN_PROFILE) for custom data extraction pipelines!

---

## 📝 License & Credits
- Data is sourced from [OpenStreetMap](https://www.openstreetmap.org/) and is licensed under the [Open Data Commons Open Database License (ODbL)](https://opendatacommons.org/licenses/odbl/).
- Processed and structured by [Abdullah Altwijri]. If you use this database in your project, a star ⭐️ to this repository is highly appreciated!