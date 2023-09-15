---
title: United States politicians’ tone became more negative with 2016 primary campaigns
date: 2023-09-15
categories: [research]
tags: [internet, politics]
---

> Sorry losers and haters, but my I.Q. is one of the highes -and you all know it! Please don't feel so stupid or insecure,it's not your fault.

Sounds familiar? This, ladies and gentlemen, is one of my favorite ever tweets by the former (and who knows? mabye the future?) POTUS Donald Trump.
Why I like it so much?
It perfectly shows what **affective polarization** looks like.
Affective polarization is an academic term for an emotionally driven diversion between good and evil, you and me, us and them.
And it's a problem:
In recent years, even decades, citizens in the United States, but also in other Democracies all over the world, perceive an increase in affective polarization.

I spent the last year of my Master's at the EPF Lausanne – a beautiful city – where I had the chance to write my Master's Thesis at Robert West's [DLAB](dlab.epfl.ch/).
For my thesis, I got my hands on [Quotebank](https://dl.acm.org/doi/10.1145/3437963.3441760), a massive dataset of quotations extracted from online news.
It contains 127 million unique quotations, crawled from 196 million news articles spread over 15000 root domains.

Together with [Andreas Spitz](https://scikon.uni-konstanz.de/personen/profile/andreas.spitz), who supervised me during my thesis, I spent roughly a year on the task of figuring out what you can do with a dataset like that.
We quickly narrowed it down to a subset of US-based quotations – most news sources in the data are US-based, and colloquially speaking, it was still enough.
Our efforts resulted in a simple finding: 

> United States politicians’ tone became more negative with 2016 primary campaigns

Not really surprising, is it?
To be honest, no one was actually surprised by the outcome of my analysis.
However, I was surprised by how perfectly the rise in negativity aligned with Donald Trump entering the political stage.
And, while it might be apparent that Mr. Trump has an inherently emotional way of speaking (one could say he mastered the art of "affective polarization"), what I didn't expect was that the change in tone was not alone due to the fact that the new POTUS had his own way of communication.
By aggregating over various speaker attributes, such as gender, party attribution, and speaker verbosity (which, if you want so, is loosely related to popularity), our research revealed that the rise in negativity was a holistic one: The political debate during Trump's term (and possible after, but we don't have data for that period, unfortunately) was characterized by an emotional, mostly negative tone across all politicians.
While Donald Trump seems to have been one of the main drivers of this trend, it affected a broad spectrum of the political debate, with unknown consequences.

Recently, we published our findings.
You can find the **open source** article **[here](https://www.nature.com/articles/s41598-023-36839-1)**.
Considering the possibilities of the data, my research covered the tip of the iceberg only.
Still, I learnt a lot handling even a small subset of the dataset only: The analysis was driven by spark-jobs, running on large clusters for hours and days, and not only once did I ssh into the UI from my smartphone to check the current progress and make sure to not crush the servers by producing memory leaks.

If you want to work on the data, feel free to reach out to me, [check the official code repository](https://github.com/epfl-dlab/Negativity_in_2016_campaign) for our paper, and [download the dataset](https://zenodo.org/record/42773118).
On the other hand, if you just want to find funny quotes, let me tell you that there is a [Quotebank UI](https://quotebank.dlab.tools/search?target=quotation&text=Sorry%2C+losers+and+haters&from_date=2008-09-01&to_date=2020-04-17) – something that was under development while I wrote my thesis and that I love to see, as it drastically reduces the threshold to getting started playing around with the data.

For me, it's time to move on: I _loved_ my small detour in the area of computational social sciences, but since then, I moved on to continue working with emotionless, modular robots. They might not be quite as fun at first sight, but believe me, they can still drive you crazy (in a good way, kinda). There are more stories to tell, but so far, let me end with another quote from Quotebank.

> It's been a tremendous run, a great time and a wonderful experience.... It's been a blast, but it's time.