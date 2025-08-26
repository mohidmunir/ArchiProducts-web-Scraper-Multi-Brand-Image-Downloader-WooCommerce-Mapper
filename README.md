# ArchiProducts Web Scraper & WooCommerce Mapper

This repository contains a **Jupyter Notebook-based scraper** that automates the process of extracting **products and images** from [ArchiProducts.com](https://www.archiproducts.com).  
It is built for **bulk product import into WooCommerce / WordPress** with full **image downloading, renaming, and mapping**.

---

##  Features

-  **Brand/Product Scraping**
  - Crawl brand pages with multiple pagination.
  - Extract product metadata: Title, Brand, Category, Description, Tags, Type, Dimensions, etc.
  - Collect product page URLs for traceability.

-  **Image Downloading**
  - Downloads **main product images**, **gallery images**, and **dimension images**.
  - Saves images in **organized folders**:
    ```
    images_archi/Brand/Collection/Category/ProductName/
        main_1.jpg
        main_2.jpg
        gallery_1.jpg
        dimension_1.jpg
    ```
  - Automatically renames dimension images as `dimension_1.jpg, dimension_2.jpg, ...`
  - Handles both **text dimensions** and **image-based dimensions**.

-  **CSV Mapping for WooCommerce**
  - Maps all scraped data into WooCommerce/WebToffee-friendly CSV.
  - Generates fields:
    - **Name, Short description, Categories, Brand, Type, Images, Tags**
    - **Attribute 1: Dimensions** (value, visible, global)
    - **Published, Visibility in catalog**
  - Supports **WooCommerce default importer** and **WP All Import/WebToffee plugin**.

-  **Utility Scripts**
  - Fixes brand names with dots (e.g., `Arrediorg.it`).
  - Re-scrapes only products with missing main images.
  - Adjusts image URLs if root folder changes (`images` → `images_archi`).
  - Deduplicates duplicate product entries.

---

##  Project Structure
ArchiProducts-Scraper/
├── Archi_products_website_scraper_project.ipynb # Main Notebook
├── requirements.txt # Dependencies
├── README.md # Documentation
├── .gitignore # Ignore unnecessary files
├── images_archi/ # Downloaded images (auto-created)
├── output/ # Processed CSV files
└── data/ # Raw scraped data (optional)
