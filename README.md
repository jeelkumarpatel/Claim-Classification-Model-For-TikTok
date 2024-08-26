# Project Description  
TikTok users have the ability to report videos and comments that contain user claims. These reports identify content that needs to be reviewed by moderators. This process generates a large number of user reports that are difficult to address quickly. 

I have built a clasification model that can determine whether a video contains a claim or offers an opinion. With a successful prediction model, TikTok can reduce the backlog of user reports and prioritize them more efficiently.  

Attributes:  
 1   claim_status              
 2   video_id                  
 3   video_duration_sec        
 4   video_transcription_text  
 5   verified_status           
 6   author_ban_status         
 7   video_view_count          
 8   video_like_count          
 9   video_share_count         
 10  video_download_count      
 11  video_comment_count       

 Key insights from EAD:  
 1) All videos are 5-60 seconds in length, and distribution is uniform.
 2) video_view_count has a very uneven distribution, with more than half the videos receiving fewer than 100,000 views. Distribution of view counts > 100,000 views is uniform.
 3) Most videos have fewer than 100 comments.
 4) The overwhelming majority of videos had fewer than 10,000 shares.
 5) The majority of videos were downloaded fewer than 500 times.
 6) There are far fewer verified users than unverified users, but if a user is verified, they are much more likely to post opinions.
 7) For both claims and opinions, there are many more active authors than banned authors or authors under review; however, the proportion of active authors is far greater for opinion videos than for claim videos. Again, it seems that authors who post claim videos are more likely to come under review and/or get banned.
 8) The overall view count is dominated by claim videos even though there are roughly the same number of each video in the dataset.
 9) Null values were found in 7 different columns.

Model Used: Logistic Regression
I have developed a logistic regression model for verified status based on video features. The model had decent predictive power. Based on the estimated model coefficients from the logistic regression, longer videos tend to be associated with higher odds of the user being verified. Other video features have small estimated coefficients in the model, so their association with verified status seems to be small.
