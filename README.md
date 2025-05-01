# DiscountOptimiser

Building AI course project

## Summary

Consumers are constantly bombarded with store circulars, weekly ads, and other printed promotions—often to the point where identifying the most relevant offers becomes a challenge. DiscountOptimiser provides a way to navigate through the information overload by compiling these ads into a single platform, analysing and organising their content, and delivering personalised suggestions based on user preferences.

## Background

Rampant inflation and long-standing economic challenges have made consumers increasingly price-conscious. While flooded with useful special offers, consumers often find the constant inflow of printed ads unmanageable. Life is a constant rush, and most deals tend to expire before one has the time to go through the pile. Furthermore, printed ads tend to be broad in scope and seldom feature several offers that truly align with a consumer’s needs. It is hard to see the forest for the trees.


## Data

The platform uses either one or two sets of data, depending on user preferences. The principal dataset consists of OCR-scanned printed ads. The special offers are then divided into categories such as vegetables, meat, dairy, beverages, cosmetics, and home appliances.

A pre-determined set of leading store chains (S-ketju, Kesko, Tokmanni, Rusta, Masku, Jysk, Motonet etc.) forms the core of the categorisation process. Their product categories are first harmonised manually, after which OCR-recognised product names from printed ads are compared to their online product listings. This set of labelled data is then used to predict the category of products from other stores’ ads. Discounted product names are first matched against the main set’s online stores. If no match is found, the category is predicted using tf-idf: comparing product names and descriptions to those in the pre-determined set.

Furthermore, each item is enriched with information such as the discount price and percentage, how long the offer remains valid, and any regional limitations.

Second, if the user prefers more tailored recommendations, they can upload data on past shopping behaviour. This can be done by OCR-scanning receipts or downloading data from loyalty card services such as [S-mobiili](https://www.s-kanava.fi/palvelut/omat-ostot/), [K-Ruoka](https://www.k-ruoka.fi/artikkelit/sovellus/mobiilisovellus), [Lidl Plus](https://www.lidl.fi/c/lidl-plus/s10021317), and [Tokmanni Klubi](https://www.tokmanni.fi/tokmanniklubi/ukk). The data is then divided into groups consistent with the harmonised categories.


## How is it used?

DiscountOptimiser is designed for price-conscious consumers who want to make the most of non-personalised printed ads but do not necessarily have the time to process them. To make their utilisation easier, the application compiles printed special offers into a user-friendly and customisable platform.

The platform can be used in two general ways, depending on whether the user decides to upload their own data into the service. If the user prefers not to have personalised recommendations based on their past behaviour, DiscountOptimiser serves as a centralised catalogue of special offers. While not automatically providing recommendations based on personalised preferences, one can use filters (product categories, region/location, discount percentage etc.) to manage the results. By providing their location, for instance, users will only see discounts that are valid in stores found within a given radius of that location. Users can also set a watch to track offers on specific products or categories, such as coffee.

If the user decides to upload personal data to the platform, past shopping behaviour (categories, seasonal fluctuation, budget etc.) is used to predict the most relevant discounts. This is implemented by providing two sets of recommendations. First, discounts are weighed based on product category patterns from the personal data. While generally useful, some of the categories may be too broad to provide customised suggestions. Hence, the second list is based on more fine-tuned product categories: the more cheese you buy, the more cheese-related products you are shown, for instance. The user can further filter the recommendations in similar fashion to the non-personalised use of the platform.

The analysis of the input data depends on its type. In the case of digital data with full product names, the customer behaviour is analysed in similar fashion to how products are categorised from the pre-determined set of store chains. With receipts, however, product names are usually shortened. Hence, the product category is determined by applying tf-idf to the names.

In both cases, the benefits are clear and consistent. While the platform can also be used as a general catalogue of special offers, making use of the AI features provides a more efficient way of managing the hordes of printed ads.


## Challenges

One could argue that printed ads are echoes from the past, and that they will be entirely replaced by digital advertising sooner rather than later. While it is true that digital solutions are rapidly growing, printed advertising continues to play a significant role in reaching customers (see Acknowledgments). Moreover, the growth of digital marketing has become increasingly restricted by recent trends in privacy. Especially within the European Union, the types of data that can be collected and used to target customers are heavily regulated both by national and transnational legislation. Customers, too, have become more willing to pay for removing digital ads from favoured services (Spotify, YouTube Premium, Meta, and so on). In the future, digital and printed advertisements will likely continue to be used side by side—both as alternatives and complements.

## What next?

To bridge the divide between print and digital and improve the coverage of DiscountOptimiser, the platform could also be enriched with digital offers. This can be done in two complementary ways:

* By scanning for digital ads, especially from major brands and stores
* Regularly scanning price changes in digital marketplaces and flagging them if the prices have been lowered. While stores have a clear incentive to advertise special offers (and hence such scanning may not represent a major improvement), there are seasonal products whose prices tend to fluctuate even without being labelled as a special offer. If this is to be implemented, it should preferably be applied selectively (e.g. vegetables and other seasonal products).

## Acknowledgments

[Building AI](https://buildingai.elementsofai.com)

[Canada Post Corporation](https://twosidesna.org/wp-content/uploads/sites/16/2018/05/CPC_Neuroscience_EN_150717.pdf)

[Kubo](https://www.kubo.fi/blogi/asiakaslehti-selva-ykkonen-kuluttajien-suosikkina-miksi-ihmeessa)
