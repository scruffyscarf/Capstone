# **Week \#5**

# **Feedback** 


### **Sessions** 

### [**Link to the folder with results.**](https://drive.google.com/drive/folders/1DnClvRLbBuQUBCHDhG0y2USsMnWJoGIQ?usp=sharing)

### **Analyze** 

### [*Link to the CutDev page with important points from feedback.*](https://www.notion.so/CustDev-for-Week-5-21d5a218c5d5807da8a2d1e3306cf45c) 

### **Iteration & Refinement** 

### **Implemented features based on feedback** 

- Completely new design. On this iteration, we have refined our design style to be more black-and-white fashion related. We have changed our coloring schema, and the overall layout  
- Implemented landing page and about page. For now, the user is first introduced to the project, and only then he has the ability to upload some outfit. Moreover, there is a new profile page, where you can see your wardrobe and provided outfits.  
- We also introduced authorization and authorization pages to the user.

### **Performance & Stability** 

### *While it is hard to calculate exact metrics on our project, since it is very biased on the machine, we can present some:*

- Overall RAM Usage: 2gb (based on Docker metrics) \- comes from models and application that we run in this project  
- Overall Disk Usage: 3-4gb \- comes from storing outfits, items and other user clothes. In future can grow dramatically  
- Full Search Latency: 0.33s \- this is latency for search on our experimentation machine (Macbook M3 Pro). This value can be different from the time you observe while running our deployed project, since here we measured exactly Search latency, without measuring other operations, such as retrieving images from the database.  
- RAM Usage during our search: \~ 300 Mb \- This includes  RAM used on local machine while performing our search algorithm and RAM used on qdrant server. 

### **Documentation** 

For the documentation of our project, we have fully comprehensive README in our github repository. This readme shows how to run the project, the chosen stack, and proposed workflow. We also have a separate file containing guidance on developing on our project. 

Moreover, we have implemented a full graphical pipeline of our search engine.

[Link to the picture](https://drive.google.com/file/d/1fCo_jtYiIIYR1LmMDl2PATtGSYcdd5MX/view?usp=sharing)

### **ML Model Refinement** 

During this week, major work on this project was done on ML part.  Before, we were relying on embeddings provided by the CLIP embedder. However, during testing of our project, we find out that for some reason CLIP thinks that sunflowers could be more similar to jackets than some other jackets. Therefore, we have researched several ways of improving the quality of our embeddings. 

- Firstly, we incorporated a new pipeline for processing outfits. Here, after YOLO have performed detection on the image, we retrieve the obtained bounding boxes. These bounding boxes were then passed to the SAM segmentation model to segment clothes from the image. Segmented clothes were then cropped from image, placed into standardized image size  \- 640x640 with gray background (gray background yielded better performance)  
- Secondly, we changed our embedding models. We have researched several embedding models \- FashionCLIP, CLIP, DINO, and etc. We have concluded that for our purposes DINO base model provided the best performance embeddings.

Moreover, our search algorithm heavily relies on vector search. Therefore, we investigate possible ways of improving our vector search part. We iterated through indexing parameters of the HNSW algorithm. Moreover, we explored quantization possibilities, and we repeated this process for each DINO embeddings model. Small table representing our experiments results below

[*Link to the picture*](https://drive.google.com/file/d/1__BFGSjeDbp-MXS8aQyX9AMZ5JfUK6UV/view?usp=sharing)

As seen, we efficiently reduced RAM usage by a factor of 16, and also almost in half reduced latency for search, while preserving best metrics. For implementation of the experiments, you can address our github directory called “notebooks". 

Using all these experiments, we found out the best configuration and parameters for our search engine. These changes and new approaches were merged into our current pipeline during this week.

**Weekly commitments** 

## **Individual contribution of each participant** 

*Bulat Sharipov \- managed team work, distributed the tasks, checked progress and wrote this report.*

*Danil Fathutdinov \- conducted ML experiments, incorporated best found parameters and models to our pipeline.*

*Dinar Yakupov \- iterated on frontend development, developed completely new design, created more pages and refined style*

*Remal Gareev \- iterated on backend development, incorporated authorization, and started developing new features*

*Victor Mazanov \- conducted Customer Development interview and made an analysis based on it. ([link](https://www.notion.so/CustDev-for-Week-5-21d5a218c5d5807da8a2d1e3306cf45c?source=copy_link))*

*Artyom Grishin \- iterated on product design, came up with new features to implement from CustDev and writed a backlog report: features to implement .* ([link](https://www.notion.so/Backlog-and-analyzing-the-custdev-22ba795c445f80a99ff3cf603c56a8f9?source=copy_link))

## **Plan for Next Week** 

- Developing possibility to choose only a subset of clothes from the wardrobe to make outfit predictions.  
- Possibility to filter outfit searches by gender (i.e. showing clothes for girls only).  
- Possibility to filter outfit based on styles (i.e. casual, official).  
- Possibility to filter outfit based on dominated color on the outfit (i.e. yellow outfits).  
- Possibility to download outfit images.  
- Iterating on new ideas and features for the application   
- Add folder distribution mechanism: creating custom folders and propagating with outfits. Build endpoints and frontend pages.  
- Possibility to download outfit images.  
- Customer development.

## Confirmation of the code’s operability 

We confirm that the code in the main branch:

*  In working condition.  
*  Run via docker-compose (or another alternative described in the `README.md`).

