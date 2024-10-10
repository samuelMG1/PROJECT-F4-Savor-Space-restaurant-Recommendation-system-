# Food Tourism: Personalized Restaurant Recommendations
## Group members:
* Nancy Maina
* Andrew Manwa
* Elsie Serem
* Samuel Gathogo
* Martin Omondi
## Table Of Contents
1. [Introduction](#introduction)
2. [Problem Statement](#problem-statement)
3. [Business understanding](#Business-understanding)
4. [Data Understanding](#data-understanding)
5. [Data Preparation](#data-preparation)
6. [Data Modeling](#data-modeling)

![Amazing Personalized Service](https://www.lsretail.com/hubfs/BLOG_5-ways-offer-amazing-personalized-service-restaurant.png)
# Introduction

Savor Space is a growing tourism and travel agency offering a wide range of services; from booking accommodations to providing tour guides and creating personalized travel experiences. Our mission is to ensure that tourists have an enriching and seamless journey hence fully enjoying their destination.

We believe that traveling is about more than just sightseeing,it's also about savoring local cuisines that suit individual tastes. Whether a tourist is looking for traditional dishes, vegan options, or a fine dining experience, finding their preferred restaurant guarantees a satisfying experience. To enhance this specific aspect of their journey, Savor Space is developing a restaurant recommendation system designed to help tourists discover dining spots that align with their preferences,ensuring a memorable and enjoyable culinary experience.

# Problem Statement
Its not easy for a majority of tourists to find restaurants that align with their tastes, especially when visiting unfamiliar locations. Lack of personalized recommendations means that they may rely on random reviews, which do not always reflect their preferences or specific dining needs. The lack of tailored suggestions can negatively impact a tourist's overall experience. The problem Savor Space seeks to solve is how to provide accurate and personalized restaurant recommendations based on individual preferences, allowing tourists to easily find eateries they will enjoy.

#### Stakeholders

* **Savor Space Management:** An interest in offering personalized and innovative services to boost customer satisfaction and retention thus positvely impacting their ROI.

* **Tourists:** They are the primary users of the system. They will benefit from the personalized recommendations

* **Restaurant Owners:** Although they are not directly involved, they may benefit from increased visibility when their restaurant is recommended in alignment with customer preferences.

# Objective

**1. To develop a robust restaurant recommendation system**- that provides personalized suggestions to tourists based on their preferences, dietary restrictions, and location.

**2. To improve tourist satisfaction**- this is done by enabling them discover restaurants that match their individual tastes, enhancing their overall travel experience.

**3. To leverage data science techniques**-these include: Natural Language Processing (NLP) and recommendation algorithms (content-based and collaborative filtering) to ensure accurate and reliable recommendations.

**4. To evaluate and improve the recommendation system**- can be achieved by using advanced models and performance metrics like RMSE to optimize the system's accuracy.


# Business Understanding
Savor Space is a tourism and travel agency that aims to provide a seamless and enriching experience for
tourists. The agency offers a wide range of services, including booking accommodations, providing tour guides, and creating personalized travel experiences. The restaurant recommendation system is a key component of this service, as it enables tourists to discover dining spots that align with their preferences.
# Data understanding
In order to come up with a cutting edge restaurant recommendation system, we opted to get real-time data from Yelp.com. The data was extracted through web scraping and a total of five json datasets were obtained. 

This restaurant recommendation system leverages two  primary datasets namely the **business.json** and the **review.json** as the had relevant information required to develop the recmmendation system.

**1) Business Dataset**

This dataset includes essential information about a variety of restaurants.

**2) Review Dataset**

This dataset provides insights into user preferences and their dining experiences.
# Data preparation
The data was preprocessed to ensure that it was in a suitable format for analysis. This involved the following steps:
1. **Data Cleaning**: Removing any duplicate or irrelevant data.
2. **Data Transformation**: Converting the data into a suitable format for analysis.
3. **Data Normalization**: Scaling the data to a common range to prevent feature dominance.
4. **Data Modeling**


# Exploratory Data Analysis (EDA)
The EDA was performed to understand the distribution of the data and identify any patterns or correlations.
The dataset was analyzed to understand trends, including the distribution of business ratings, popular restaurant categories, and the number of reviews per city. Visualizations such as histograms, box plots, and word clouds were used to illustrate key insights.

This EDA offered vital insights,the differences in the distribution of user ratings and business ratings in the dataset and what do these differences indicate about user preferences?

![alt text](image-4.png)

**Correlation between Rating and B/S Rating**
The correlation value of 0.41 indicates a moderate positive relationship between restaurant or service ratings and B/S Ratings. This suggests that as a business's rating increases, its B/S Rating also tends to rise, implying that higher individual ratings often lead to a better overall rating based on user reviews.
**Distribution of Categories**
What are the most prevalent restaurant categories and how does the distribution of these categories impact the restaurant landscape in terms of user preferences and choices?

![alt text](image-5.png)

**Distribution of Restaurants across the citties and states**
The distribution of restaurants across cities and states is uneven, with some cities having a higher concentration of restaurants.

![alt text](image-6.png)
From the analysis above it is clear that philadephia has the highest number of restaurantst city. Following, but not as closely, is Tampa, indicating a notable restaurant presence. In contrast, the cities of Edmonton and Santa Barbara have fewer restaurants, making them less common in this dataset.
**Popular Restaurants**
The most popular restaurants in the dataset are those with high ratings and a large number of reviews. These restaurants are likely to be well-known and have a strong reputation among users.
![alt text](image-7.png)
**Review Word Cloud Analysis**
The word cloud analysis reveals the most frequently used words in the reviews, providing insights into user preferences.
![alt text](image-8.png)
The word cloud visually represents the most common words found in the positive review texts, where the size of each word in the cloud corresponds to its frequency in the reviews.

# Modeling
In this section we created a recommendation system using the datasets to solve our main problem.
We also did some sentiment Analysis and performed some text preprocessing such as:
-Feature engineering : further feature engineering of the columns to meet the required specifications for analysis eg aggregating text reviews, creating new columns from the existing columns .. etc
- Removal of Punctuations and Removal of Stopwords - we used the **RegexpTokenizer()** method
-  Stemming - reducing words to their root meaning , we used the **SnowballStemmer()** method
- Word-Vectorization - splitting text data into a vector of individual words for further and easier nlp analysis, we used the **TidfVectorizer()** method that vectorizes text data and calculates their respective Term Frequency - Inverse Document Frequency (TI-IDF) values.

## Content-based Recommendation System:
We developed a content-based recommendation system using the cosine similarity matrix to match restaurants with user preferences. By comparing the similarity between different restaurants and the customer's specified attributes, where we can recommend the top N similar restaurants based on their input.

<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe srcdoc="&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
    
    &lt;meta http-equiv=&quot;content-type&quot; content=&quot;text/html; charset=UTF-8&quot; /&gt;
    
        &lt;script&gt;
            L_NO_TOUCH = false;
            L_DISABLE_3D = false;
        &lt;/script&gt;
    
    &lt;style&gt;html, body {width: 100%;height: 100%;margin: 0;padding: 0;}&lt;/style&gt;
    &lt;style&gt;#map {position:absolute;top:0;bottom:0;right:0;left:0;}&lt;/style&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://code.jquery.com/jquery-3.7.1.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js&quot;&gt;&lt;/script&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap-glyphicons.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.2.0/css/all.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css&quot;/&gt;
    
            &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width,
                initial-scale=1.0, maximum-scale=1.0, user-scalable=no&quot; /&gt;
            &lt;style&gt;
                #map_6419dc52154b10221083b0f085ddc16e {
                    position: relative;
                    width: 100.0%;
                    height: 100.0%;
                    left: 0.0%;
                    top: 0.0%;
                }
                .leaflet-container { font-size: 1rem; }
            &lt;/style&gt;
        
&lt;/head&gt;
&lt;body&gt;
    
    
            &lt;div class=&quot;folium-map&quot; id=&quot;map_6419dc52154b10221083b0f085ddc16e&quot; &gt;&lt;/div&gt;
        
&lt;/body&gt;
&lt;script&gt;
    
    
            var map_6419dc52154b10221083b0f085ddc16e = L.map(
                &quot;map_6419dc52154b10221083b0f085ddc16e&quot;,
                {
                    center: [40.2101961875, -75.2236385919],
                    crs: L.CRS.EPSG3857,
                    zoom: 7,
                    zoomControl: true,
                    preferCanvas: false,
                }
            );

            

        
    
            var tile_layer_90a7f1430d01c9228a57104bad90b32f = L.tileLayer(
                &quot;https://tile.openstreetmap.org/{z}/{x}/{y}.png&quot;,
                {&quot;attribution&quot;: &quot;\u0026copy; \u003ca href=\&quot;https://www.openstreetmap.org/copyright\&quot;\u003eOpenStreetMap\u003c/a\u003e contributors&quot;, &quot;detectRetina&quot;: false, &quot;maxNativeZoom&quot;: 19, &quot;maxZoom&quot;: 19, &quot;minZoom&quot;: 0, &quot;noWrap&quot;: false, &quot;opacity&quot;: 1, &quot;subdomains&quot;: &quot;abc&quot;, &quot;tms&quot;: false}
            );
        
    
            tile_layer_90a7f1430d01c9228a57104bad90b32f.addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
            var marker_9b29cc6016be0a4b7b1e63dbf57d83d8 = L.marker(
                [40.2101961875, -75.2236385919],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_7d7af165d97132309863a4b1445f2fd5 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_26bf86e977276450b1fb1185de8b6726 = $(`&lt;div id=&quot;html_26bf86e977276450b1fb1185de8b6726&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Turning Point of North Wales Stars: 3.0 State:PA, City:North Wales, Address:1460 Bethlehem Pike &lt;/div&gt;`)[0];
                popup_7d7af165d97132309863a4b1445f2fd5.setContent(html_26bf86e977276450b1fb1185de8b6726);
            
        

        marker_9b29cc6016be0a4b7b1e63dbf57d83d8.bindPopup(popup_7d7af165d97132309863a4b1445f2fd5)
        ;

        
    
    
            var marker_92857077dc59e4afcf78aef9bbb3fd59 = L.marker(
                [32.2072326, -110.9808639],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_d06ef4351e181aee37761ef7c1c2d587 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_d18048fc3ad4efb605e022748e538e87 = $(`&lt;div id=&quot;html_d18048fc3ad4efb605e022748e538e87&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Kettle Restaurant Stars: 3.5 State:AZ, City:Tucson, Address:748 W Starr Pass Blvd &lt;/div&gt;`)[0];
                popup_d06ef4351e181aee37761ef7c1c2d587.setContent(html_d18048fc3ad4efb605e022748e538e87);
            
        

        marker_92857077dc59e4afcf78aef9bbb3fd59.bindPopup(popup_d06ef4351e181aee37761ef7c1c2d587)
        ;

        
    
    
            var marker_fe64f44920980a4bf5a05f64d27719f8 = L.marker(
                [40.0798480557, -75.025079772],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_ad6c554b82a041fd895e88b0cfc3bd32 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_7aaabcd45dabaa4fd0d9d7de81234263 = $(`&lt;div id=&quot;html_7aaabcd45dabaa4fd0d9d7de81234263&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Zaika Stars: 4.0 State:PA, City:Philadelphia, Address:2481 Grant Ave &lt;/div&gt;`)[0];
                popup_ad6c554b82a041fd895e88b0cfc3bd32.setContent(html_7aaabcd45dabaa4fd0d9d7de81234263);
            
        

        marker_fe64f44920980a4bf5a05f64d27719f8.bindPopup(popup_ad6c554b82a041fd895e88b0cfc3bd32)
        ;

        
    
    
            var marker_e30c88c1255bda4a15f5569de8c08359 = L.marker(
                [29.962102, -90.087958],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_4b89da55140b3514d91c0a714cf1fffc = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_d95afdce18feefa28d9e9bd72a9cf0fc = $(`&lt;div id=&quot;html_d95afdce18feefa28d9e9bd72a9cf0fc&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Melt Stars: 4.0 State:LA, City:New Orleans, Address:2549 Banks St &lt;/div&gt;`)[0];
                popup_4b89da55140b3514d91c0a714cf1fffc.setContent(html_d95afdce18feefa28d9e9bd72a9cf0fc);
            
        

        marker_e30c88c1255bda4a15f5569de8c08359.bindPopup(popup_4b89da55140b3514d91c0a714cf1fffc)
        ;

        
    
    
            var marker_6289dd042de9ea0fad6160e59df291ab = L.marker(
                [39.9380132, -75.1481307],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_bd36caa83478b7203b629e65a4f69924 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_e3ba09e14c1f7f81061726dbdbc07aa7 = $(`&lt;div id=&quot;html_e3ba09e14c1f7f81061726dbdbc07aa7&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Dmitri&amp;#39;s Stars: 4.0 State:PA, City:Philadelphia, Address:795 S 3rd St &lt;/div&gt;`)[0];
                popup_bd36caa83478b7203b629e65a4f69924.setContent(html_e3ba09e14c1f7f81061726dbdbc07aa7);
            
        

        marker_6289dd042de9ea0fad6160e59df291ab.bindPopup(popup_bd36caa83478b7203b629e65a4f69924)
        ;

        
    
    
            var marker_e5221fc6b25f80cb3664914c83f97a2e = L.marker(
                [40.4075374562, -75.3388251276],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_4323cd6027c23f31bcdd13e7488f06e9 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_db162efd3ca4ae0fca5f3582a5fc7b18 = $(`&lt;div id=&quot;html_db162efd3ca4ae0fca5f3582a5fc7b18&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Fries Rebellion Stars: 3.5 State:PA, City:Quakertown, Address:1441 S West End Blvd &lt;/div&gt;`)[0];
                popup_4323cd6027c23f31bcdd13e7488f06e9.setContent(html_db162efd3ca4ae0fca5f3582a5fc7b18);
            
        

        marker_e5221fc6b25f80cb3664914c83f97a2e.bindPopup(popup_4323cd6027c23f31bcdd13e7488f06e9)
        ;

        
    
    
            var marker_331473760c64ac64413e5e8c89d5c543 = L.marker(
                [34.4169836, -119.6955563],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_a6ae1539970f147a9b30c25e75e651b9 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_d47159da97279f8c9ae65c92b7423ba5 = $(`&lt;div id=&quot;html_d47159da97279f8c9ae65c92b7423ba5&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Hibachi Steak House &amp;amp; Sushi Bar Stars: 3.5 State:CA, City:Santa Barbara, Address:502 State St &lt;/div&gt;`)[0];
                popup_a6ae1539970f147a9b30c25e75e651b9.setContent(html_d47159da97279f8c9ae65c92b7423ba5);
            
        

        marker_331473760c64ac64413e5e8c89d5c543.bindPopup(popup_a6ae1539970f147a9b30c25e75e651b9)
        ;

        
    
    
            var marker_b70ed8a4c1b4e8ff70bf3ea9482eaf69 = L.marker(
                [39.7591692208, -86.146494347],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_a4a975fbdd6f9125a8c3c4ed28123a36 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_39cafe6d8dcb324cdceb79b23aae1238 = $(`&lt;div id=&quot;html_39cafe6d8dcb324cdceb79b23aae1238&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Milktooth Stars: 4.0 State:IN, City:Indianapolis, Address:534 Virginia Ave &lt;/div&gt;`)[0];
                popup_a4a975fbdd6f9125a8c3c4ed28123a36.setContent(html_39cafe6d8dcb324cdceb79b23aae1238);
            
        

        marker_b70ed8a4c1b4e8ff70bf3ea9482eaf69.bindPopup(popup_a4a975fbdd6f9125a8c3c4ed28123a36)
        ;

        
    
    
            var marker_0cfffcc2f62e745f304a6442f74f15c9 = L.marker(
                [38.6324938, -90.4064437],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_8cd91b99b287d187a2b035ab6c8fae20 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_0f3881c75f392e3576755fc0fb98a974 = $(`&lt;div id=&quot;html_0f3881c75f392e3576755fc0fb98a974&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;Brio Italian Grille Stars: 3.5 State:MO, City:St Louis, Address:1601 S Lindbergh Blvd &lt;/div&gt;`)[0];
                popup_8cd91b99b287d187a2b035ab6c8fae20.setContent(html_0f3881c75f392e3576755fc0fb98a974);
            
        

        marker_0cfffcc2f62e745f304a6442f74f15c9.bindPopup(popup_8cd91b99b287d187a2b035ab6c8fae20)
        ;

        
    
    
            var marker_4295f332fc76cf149256272f8f20122e = L.marker(
                [39.949529, -75.152139],
                {}
            ).addTo(map_6419dc52154b10221083b0f085ddc16e);
        
    
        var popup_49af0da7b91f94076daea9c451e07638 = L.popup({&quot;maxWidth&quot;: &quot;100%&quot;});

        
            
                var html_2460d314ad32c57f23947200543939f9 = $(`&lt;div id=&quot;html_2460d314ad32c57f23947200543939f9&quot; style=&quot;width: 100.0%; height: 100.0%;&quot;&gt;LaScala&amp;#39;s Stars: 3.5 State:PA, City:Philadelphia, Address:615 Chestnut St &lt;/div&gt;`)[0];
                popup_49af0da7b91f94076daea9c451e07638.setContent(html_2460d314ad32c57f23947200543939f9);
            
        

        marker_4295f332fc76cf149256272f8f20122e.bindPopup(popup_49af0da7b91f94076daea9c451e07638)
        ;

        
    
&lt;/script&gt;
&lt;/html&gt;" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>

The above is content_based function  that uses content-based recommendation techniques to provide restaurant recommendations based on user input preferences, restaurant names, or user-defined text. The recommendations can be filtered by minimum rating and location and are visually presented on an interactive map if specified.

## Deep Neural Networks:
We used  Keras deep neural network to implement a recommendation system and tried to improve our RMSE scores by using neural networks. and got that:
Number of Users:  34497
Number of Restaurants:  3720

The baseline model had a training RMSE of 0.3896 and a test RMSE of 1.3671 hence being our better neural networks model with the lowest test scores.

In all the models SVD emerged to be the best RMSE score of 1.25

## Conclusion
In conclusion, this project successfully developed an interactive and user-friendly restaurant recommendation system that offers personalized dining suggestions while considering various factors influencing restaurant ratings and user preferences. The advanced recommendation algorithm enhances users' dining experiences by providing tailored recommendations.

We achieved specific objectives by designing a user-friendly website for easy interaction with the system and conducting in-depth analyses of the factors affecting restaurant ratings. This understanding helped refine our algorithms to deliver relevant suggestions.

Additionally, we utilized Folium for geographical data visualization, creating interactive maps that highlight geographic trends in restaurant recommendations. These maps make the experience more engaging and help users discover new dining options in their preferred areas.

Overall, this project has effectively delivered a comprehensive restaurant recommendation system, enabling users to access personalized suggestions based on various factors and geographical trends, thus enhancing their dining experiences.

## Recommendations
* User Feedback Integration: Actively gather and incorporate user feedback to enhance the recommendation system.

* Improved User Profiles: Utilize collected data to deliver more personalized restaurant recommendations.

* Refined Algorithms: Continuously improve the recommendation algorithms by exploring advanced machine learning techniques, including deep learning, to boost accuracy and personalization.

* Geographical Expansion: Gradually broaden the system's geographical coverage to include more regions and cities, offering users a wider selection of dining options.

## Future Improvement Ideas

* Community Engagement: Encourage users to share their dining experiences and reviews. Implement social sharing features to foster a community and facilitate peer recommendations.

* Real-Time Updates: Provide real-time updates on restaurant information, including opening hours, special offers, and menu changes, ensuring users have the latest data.

* Food Delivery Integration: Partner with food delivery services to enable users to order for delivery or pickup directly through the recommendation system.

* Advanced Machine Learning: Investigate advanced machine learning algorithms to further improve recommendation accuracy.


This project was developed by Andrew Manwa, Elsie Serem, Martin Omondi, Nancy Maina, and Samuel Gathogo. Contributions are welcome—please fork the repository and submit a pull request with proposed improvements and join the team.S

# License
This project is licensed under the MIT License. 
