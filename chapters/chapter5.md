# Week 4

Welcome to another Week. Now, I am getting more clear knowledge about the Project, CERN, CMS, Experiments at CERN, Work Culture at CERN, About Physics, World's working and lot more. 

I am really enjoying learning more and more about LHC. I must not say learning but It is more like knowing. I am loving to know more about LHC (Large Hedron Collider) and also about Higgs Boson particle. These things are way beyond my project work but I am in love with things. They are really making an impact to lives on this planet. And it have new possibilities and capabilities. I really love things at CERN by this amount of time working here. 
Meanwhile, I am also about to participate into WebFest which used to be a weekly hackathon but this year, It is stipulated over the month of time. And luckily, Their event theme is **Environment** and one of the project theme is **Data Visualization**. Thanks, To my GSOC Project, I will be having a good idea about the project compared to the case if I was not a part of GSOC under CERN. Let's rock and roll into the CERN's Webfest. Now, Let me give an update about my Week so far.

Starting off from Monday, In the meeting, I was not at my home so I was facing fluctuations in my internet connections and was barely able to discuss with my mentor in the meet. Still we got few points cleared for the week. Actually, This week was about Scatter Plots but due to my involvement into the wedding, We had settled on shifting the Scatter Plots to next week which was also being occupied for Advanced Scatter-Plots. Then we discussed a few thing about the statistics to be derived from the existing metric and the new ones to be added soon to the web.  I then got a sudden thought of breaking down the difference report separately from the raw data because the diff report was of more importance to the developers. And then I got a "YES" for doing so. And we ended the meeting with poor internet GoodByes. 

Now, Coming to the work. My mentor already provided me the extra data to be added before he would go to **Brazil** for his vacation. For the first 2 days, I was busy with functions in the cousin's wedding. That Simply means I was off from my work. Indian marriages have a lot of traditions and customs to be followed. And being a brother, You have many different roles to be played in the wedding. Then for next 1 day I was again in the bus coming 125 miles back with 50 more miles being added before coming back to my home while performing other half of tradition which was done after the marriage. So, Another day off. Meanwhile, On Sunday I had a Mid-Eval so at last moment my mentor from C4GT popped up saying to me he required a major change. We toiled for 2 days and made the stuff being done. And I am glad that my C4GT project is also adding a lot of value into the Indian Government's Infrastructure. So, This whole week, I have done no work. 

Seriously, You would be like - " Hey ! What the heck is wrong with you ? If I have done no work then why do on this earth the page for Week 4 Exist ?" Cool Down reader ! I was just joking. But yeah ! Joking doesn't mean lying. I did worked only on the Sunday afternoon and night and late night. I had speed run into my project on Sunday. I included new reports, Updated the Colouring to come out more generically, Popped up a difference tab out from the main raw reports. Fixed the sizing of the the table cell's height. And closed the week on late night of Sunday but better to say on early morning of Monday ! It was really a speed run which I did last time as a part of some hackathon. I love speed runs. They help you get a lot of things done in very short amount of time. It was not new for me and I am used to it so It won't affect my performance. I have practiced them a lot.

> What is speed run ? 
>
>```Getting to the main concluding goal as quickly as possible, regardless of how much is unlocked```

I also want to share about how I made the colouring more generic through the snippet.

```JavaScript
 const max_array = [];
        numeric_columns.forEach((i) => {
            const value_array= [];
            data.filter(d => {
                if(!isNaN(d[i]) && isFinite(d[i])){
                    value_array.push(d[i]);
                }
            })
            
            max_array.push(d3.extent(value_array));
        }
```
The above snippet is using a D3.JS property which is `d3.extent` which will return you with an array of two elements one which would be minimum of all the elements and other would be the maximum of all the elements. 

Now the math which I currently use for colouring is Lower 5% of the values would be green and Upper 5% would be red and in between I use white. But I still feel there is something not so good with my math behind this. I am sharing the snippet below for reference. I will be fixing this as soon as I get to know more clear insight about this statistics. 

```JavaScript
SOME_ELEMENT.style("background-color", d => {
            if(numeric_columns.indexOf(d.column)!=-1){
                const max_col = max_array[numeric_columns.indexOf(d.column)]
                return d3.scaleLinear()
                         .domain([5*max_col[0]/100,75*max_col[1]/100,95*max_col[1]/100])
                         .range(["green","white","red"])(parseFloat(d.value));
        }});
```

In the domain array, The 3 values comes with `[ 5% of min, 75% of max, 95% of max ]` and other two coming out from the extent with two values in [0] and [1] as min and max respectively. This comes over the case where I have If else loops for each metric in specific which was the worst idea for mankind. Currently this doesn't look good, But soon it will be definately improved. 

Also, My GSOC Blogs which are mere version from this book itself but written in more official manner have been merged with the CERN-HSF site. And they used codespell for spell check. I had few spelling errors which were checked by codespell and then I changed those and got my changes merged. I am now planning to add codespell to my GSOC book for more better Automation. You see, How you can learn a little things from open sourced program. Automation just saved time for PR reviewers not to worry about spelling errors. I also have an open issue on my GSOC Book repo for spell checks which now I am feeling was a dumb idea. Now, I will also integrate codespell to my GSOC Book.

End in End ! We won't have meetings this week. So, until next week we have already planned to bring out the scatter plot from the existing CSVs which we have with us. And below are the snapshots as per our beloved reader's tradition who looks at the screenshots at the end of every chapter. If you read my book ! I will be really thankful to you for my life. I am not so good at portraying the things, Still you stick by my side and read this book daily, You owe a huge **"THANK YOU"** from me. 

---
![image](https://user-images.githubusercontent.com/79367883/178314121-251bc343-46c9-497b-9e01-d054555a666b.png)

![image](https://user-images.githubusercontent.com/79367883/178314262-c0ed6553-7564-44ab-ab7f-6cde31c3be08.png)

