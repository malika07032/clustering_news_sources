# Clustering Kazakhstan’s popular news sources
Personal Project
Author: Malika Parkhomchuk

Part 1: Identifying popular news sources (part1-Modified.html)

1. Gathered recent tweets according to query words
2. Gathered expanded urls from tweets
3. Created a data frame of all the gathered links and their source domains
4. Got the top 30 news sources by the frequency of occurrence

Conclusion for Part 1 of the project:
Most of the links were retweets of other tweets, so that was not very helpful for my investigation of news sources. However, there are still alot of interesting sources to look at. For instance, egov.press is Kazakhstan's governmental source for getting information on documentations, pension, social security and etc. tengrinews.kz, inbusiness.kz, kaz.orda.kz, egemen.kz, akorda.kz, inform.kz, ktk.kz, baigenews.kz are big news portals that mostly work of governmental orders. azattyq.kz, vlast.kz are knows and popular independent sources of information. Also, people from Kazakstan use Youtube, Instagram and TikTok to look out for the news.

Part 2: Classifying Kazakhstan's News Sources

1. Researched independent and government-funded sources and got their twitter ids
2. Got followers of each news source using the Paginator (Twitter API)
3. Created a function that calculated the Jaccard Index of followers of two sources to determine their similarity
4. Implemented this function to find the Jaccard Index between every source and create a 23x23 matrix
5. Built an unsupervided model accroding to the matrix
6. Analyzed the results

Conclusion for Part 2 of the project:
Agglomerative Clustering news sources by euclidean distance of Jaccard indeces resulted in 3 main brancehs: 2 big groups and 1 branch with only one source. The news source that corresponds to the small branch is typically considered as a government-funded source @LiterKZ. With recent violent protests in Kazakhstan their page on Twitter haven't posted anything, but that must be due to the fact that there is an Internet blockage in the country. The next branch is a big group of government-funded sources. However, 3 independent sources were missclassified: @Radio_Azattyk, @AzattyqRadiosy, @Vlastkz. These sources are actually one of the prominent independent news in Kazakhstan. I assume that they were missclustered, because they have a big number of followers. Most independent sources have a modest amount of follower in comparison to government-funded ones. The third branch includes only independent sources.
Looking at the results of the cluster model, turns out it can pretty accurately classify the news sources when using Jaccard Indices as features to determine the similarity between the sources. However, the number of followers of independent and government-funded sources is very unbalanced, because independent sources had way less followers, so the similarity index between independent sources was very low. To conclude, I was able to find out the popular news sources according to Twitter users, and classify the news sources by building clusters.
