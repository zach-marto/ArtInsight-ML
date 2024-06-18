## Overview
We developed an AI model that quantifies similarity and dissimilarity between art pieces by using language as an intermediary - in order to address the limitations of comparing art purely visually. We essentially aim to capture the contextual nuances of artworks in language descriptions. Here is our model workflow - where paintings are processed through various layers to map onto distinct ordering of predefined attributes (show example for an image). These attributes are then utilized to compute dissimilarity scores between art pairs using our similarity functions.

![model_workflow_image](https://lh3.googleusercontent.com/pw/AP1GczN7HyjukDb1K17RLqSt84QkpPw3QZCBQWM0cs7AIETnz0Xxq2NfI4WiTy5mM9IPbzY-6Cn08GN5kKKMc74u5Ea6NE6uAgutpAuOsm_dXnGM68tGTzF44Ym47H9Dq5lHYetGJk9gl1Pu552kdA0n47Ex=w1000-h665-s-no)

## Our Models In Action!
We present research-based evidence to demonstrate the effectiveness and consistency of our similarity functions by using art-analysis domain-specific proofs.

#### Comparing Portfolio Pieces By Temporal Distance
We wanted to test our hypothesis that across one artist’s portfolio, pieces created closer together in time would be more similar than pieces created further apart in time. To test this, we took 20 Picasso paintings over a timespan of 40 years. We put them through our model and plotted the dissimilarity scores between each pair of images. We found that an increase in absolute time difference between paintings was correlated with a higher dissimilarity score, supporting our hypothesis.
![pieces_by_yr_diff](https://lh3.googleusercontent.com/pw/AP1GczO8h8A2QBsZh_jMlRWGJUCoNkUN_BJbosAvLlhyw4R0E7kn07S2fRVFpTxGAnZQsrf65Pi5NASCCV8R130RWdwqnkn_HLPGK_ST0fUMlPlMmcg4E9Y_qifh_Q58lbZAJIbKUlJ9ZhFA1PrOXi5nmIso=w851-h551-s-no?authuser=0)

#### Comparing Pieces Across Different Portfolios
Another hypothesis that we tested was that paintings from a single artist's portfolio would have lower dissimilarity scores when compared to each other than when compared to art from a different artist. We assumed that an artist's work tends to be more uniform in style, and that our pretrained model would be able to detect those nuances and rank the comparisons accordingly. To test this, we ran a sample of 12 paintings, between Raphael and Frida Kahlo, through our dissimilarity function and plotted the scores. As expected, the average dissimilarity scores of paintings by the same artist were consistently lower than paintings between different artists. This pattern also consisted between any two artists that we’ve tested from the WikiArt dataset.
![similarity_all_attrs](https://lh3.googleusercontent.com/pw/AP1GczPfIS1iQsN5wvfeh1PYlM9E-EhjP6YWNXoFlEvT_e5KeIU1JOpIuKGo0kq2aNmhmuaycBkIJB1uKQ0Tm-w2cM3DHuRtYRVZplYLjtxLgahtm6etPizCGwuocB27LF5-Mzw74hrXX6MS6uYidSbDHCg2=w850-h551-s-no?authuser=0)
![similarity_one_attr](https://lh3.googleusercontent.com/pw/AP1GczPWKLuYEw19em97D2o12Hucm09ycTLYUqjuYY83uO9YNtvFO6mqtXyDQ3d6l20bt7FmJs21G5VyNPhVneN_kTKreCOxlxEhTvdIqdfWAfffIgE7ZZ0swixcMlIL0SHUWqvUSDCRz_I-_AB1lWX--_e2=w877-h551-s-no?authuser=0)

#### Real-World Demo
We'll now exhibit the model's use case proficiency in identifying the most similar artworks from a diverse set of 10 pieces, unraveling connections across time periods, cultures, and styles. 
![ten_pieces](https://lh3.googleusercontent.com/pw/AP1GczNcZ240V6qowO6_VAOiOHmDuOcWYZJWXRj9wa6sMkbaE4W4lOZ3ZH3c52SMHbJH-BqnHf-ZqlHsfFIwtPqFkydPQwsr1NLD-fJPsoOBAsJixAV9PKtznTsI6Um7tqeXusufCxoXj62ADHRCguLTtq73=w1591-h895-s-no?authuser=0)


Across these 10 images, our model produced the following most similar pairs the following themes:

##### Color Palette:
![color_palette](https://lh3.googleusercontent.com/pw/AP1GczNi79h1w45twVfXy_3iWh8l02jSITDm1uZmPZiK9pLc1OydqzwCrZWFTjcDecNyyCXn-9i7njvAQ-XU-OHvcZLrtxjGFG3cr3Rmj0DLRuDx_HfkekEHcBh47LOsBlzB6DJUzAlJl8iGwx8bMQKyK8Tmr8xiShWox6dM_mzWYSJ-hUMT48NhwASXO_MAWOPkZmiPjvoA1Or8jGM4TxeHS77jpyjKVRck8aeza2UWVoPFEqhr3S3R2hW-MNgPVhdt0xfpIlGBMvdIo05Jg1dNuLUyM3g0NMhxaup6a7DupfWJGpQGRh5O5NIW-tDVeTq6SA8WjzRAjtyzIMmaQ5qzZIZhZWkZHnyr9RRXdVmjxyCLKqhxh9Jf-rGuCDUooB_cgo3gjezGnXlNkFKXlU--KaiS8BWg7WdnaZ_JXNwvpJMmIZGIgBHMWt_oCD_LRCrHhPhjsUZx9oRw754jRmMvOp_6XZDy8G9UPADn7AS-m7H70uqGAYrXEDW_ffFuQ4SXQZeaHiDGeFkC1k4AAcB_1TBO8bBlOAAdNa9kelrx5kVbbPI0zZ41oPLFVxReOsQ_X-JKjWACHccKnxjdQrcWzdcsobwcmYO4055AO6HnH30xp81-7jJyE_Tv0afQaSlAxrAQxA_Te2VGMT4rEETLU4kTqrZfxcU_g7jjHSGpcttw1LMDtksBZC4FUsHLvZoYp8L4QIFeOVRw1gIthzMz75XDr598JtOn7YGtVv4B8PThILAN1--fv-ZSCvGOawefUzzb3oBK8J4pDxEJETEhxWq8tYiGDfpX0AIQd4Rcpo36eUTsfdX5iVsZsGbp2vZrf6U0ZqGWcFNe_1JQo6KZTtT6m_ibsUg7J1NduP1Qjo_vxn19jXEY6ncjvu_PsvmQiOMs9oASzq6Y43ZC8oWvuYU5E8c=w1591-h895-s-no?authuser=0)

##### Subject Matter:
![subject_matter](https://lh3.googleusercontent.com/pw/AP1GczPHnLWzkh5VXXn0O7yxQDPX_fOhhYMSmBGNMd087WXoTdr-vmkEFzocmkP9opHdKAxhdQkWF7QdeuDeTJhZQ8B2Wb3kEODQHiVyH0tt7lxicpwZK3O7RV4CdCs2rU6gVD_r5Whex37x8RlZzNZ3oLVkh1zk5B75eeSp2CTfRzxzPluAlZzyhXJkLt9GzovzUDGqLpoq8zd1P7aCPOHhdjKOeXBsS_RKttSNsx7YVHCVosdYGM1PKrEWLge0rl75KjfDKL2sJihx2oY0LhwovmayPv6IRKEKT-mAYCi08HnpjBDPTG9-2fwZCDfEKG7dMn_gRKaCmgyzQHFK-AmEpXblELVL66kN21g9Fp8aMuD7YptKsPYHulxjwX_uMAntLu7YvFSZ3lxjQnWr-gp9Uk9qnBWuAn32g09LV5fe0rISFv0RC6eEKxGzyNe8crUEm8TnxgjA9MFplYwpf4RPs1DVex_BFpiZAU-apTH3yH2sfXggV7yNalZ_XWAkziI4H0kB24NSQdeHFZSXVlGnXsJzATIDFlJFPYW59tnn9oORS4weinbTlKGCjSp0zpozlKQVBhFG1jYoo0N9YvwYjh43huFX5Gp8jziklr0euX8s17ARWJYpN9EqPLIEygKS4sr15eNU6ebQUXRWtz0FAx3bNpFhz5J4KXK3XtJ1wwTE-Bz0GybY8B0cILQLepL8TGzbsWbT7ki2ozkCvz-S_1UhDAiFchfnxNuugKOuSkLK1XcLaKOquAxblrCNUkaL7fopXBv4En1m0sc0PI1a07WW27MxunMWRWmiedHMn2KDfOr7HaNdAFjnctVpmEqv2gvEeKhtO-iDFIOWr0lMqtflpzE7NbYZq0dVxlUUNOq2BNhm30ul_IAi_7o5Qb1o-xbh1v9-q_Ee8NQnbFIqaIJQOT0=w1591-h895-s-no?authuser=0)

##### Mood/Emotion:
![mood_emotion](https://lh3.googleusercontent.com/pw/AP1GczNWVLFUeszDfjb8Gt9JemQTEUZEbRKw5klZ586NJC3VNPDcVO4gktvVNHQEpSyfdtnOyPnuN6uff2cpKTb50NsN9jGybKMkUHPANVOrr-Bv5of9Egk91XvUHllwPxFk4liE38ZvEroH5OzSS5u8vkh2fFSZneofDn1HTQ-6OjnZjQ2mHOaV3fOKq6LeWxEajE7irn6-uC07RAPnf_FJro4EJdJs75a8ZVvu37QWnEm7kIf4cmh2914tRlL-ENgidk-K5ol9b49d8iJfd9YSfH3__wrhsGJ7NrqdeCGqecH1ZsFrpbDIz3TpiZA0Df9XsJEqU8pJd2DjZatbbHEiGYwsFJgv11Z28UUwC99qqe6jfueMHjdDGbPFLJLTXTmUm5XbKob-4UVH6fCr4w3PjYx9ljONNhtHFeTMGlyEe-cfwCjYZSWGcAkT3lchl2MVOZTfF15WqIBC_7HzFEsmcUafFdUw_5lkIUnNpxdqVhFxmZswdQOqxmhnfLGEOTq5Dva76zlP-WC9ytcB1xeCn_DSlDGrKKl9101B8Ifto3unZIaJXMu7Bw-JZLWeu8DW6eLth4dso9qGHJQPH7Z54gO4t-6VslstuVJZn6Y-tj2YhPcb7aS2pmiaXeKDfPhxl4-j6LCoLHWZI1OwF4jdLmhlLauOk-01Cou7ETslPrAqJQOlr1__D2nMs5PPxT8ZlX4V9IsjwM8w7xM12s5DIe1w5zeKqdKNviP8obMyx7icLyzYABNLNfPp0tWmdnuyA9MxMKnMHX2Lt-hrqR3QxuQzoYXoTxtmMyWfKp_YuAINKN_1bDpgg82_4gEXRcL0brEqv6AhOANMlFq5n9cS9MCFXlTDDwM0wT6L_jJLAddqUix907LplSeopIkhbNKoFtSzV6EmN-LZPU1D6ngfSfnJ_KI=w1591-h895-s-no?authuser=0)

## Motivation
This project aims to explore the application of machine learning in the realm of art analysis by using
advanced techniques to extract themes and nuances from images. The primary motivation
behind this idea is to offer new insights into artistic content, thereby enhancing our understanding
of art.

One of our key implementation ideas is to develop a novel approach that serves as an inverse to existing
methods, such as Stable Diffusion models. By converting images into textual representations
and subsequently condensing them into coherent (synthetically designed) themes using
autoencoders, we seek to unveil latent artistic motifs that may not be immediately
apparent in a given art using natural language as the fabric. This could help quantify
similarities between different artistic works across countries, cultures, and periods.

Furthermore, we also seek to enhance the interpretability of our neural network implementation and
understand how our model derives meaning from images. Through the incorporation of skip
connections and analysis of intermediate token representations in the hidden layers, we
want to show how our model derives meaning from visual data through the natural
language evolution of the embeddings in each subsequent hidden layer. This is also going
to integrate a level of transparency into our model.

Our project also harbors the potential to evolve into a research idea as we intend to investigate
performance disparity between image reconstruction using convolutional layer embed-
dings and textual representations as the intermediary medium, and document which
approach is better at capturing the various kinds of artistic nuances. Additionally, we also
want to explore if using images as an additional layer of reconstruction can improve the
natural language summarization/compression capability of our autoencoder, in contrast
to simply training our autoencoder on only textual description reconstruction.

In conclusion, our project aims to create a tool that performs classification on images using natural
language as the medium. By implementing interpretability and synergy between image and text
encoding, we also intend to research autoencoder performance and token summarization performance
for image-to-text-to-image and text-to-text reconstruction.

## Problems Encountered and Solutions Found
#### Compressing BERT Vectors
One challenge we encountered during the project was devising a method to compress a matrix composed
of BERT vectors into a matrix composed of Word2Vec vectors while retaining as much information
as possible. This task involved compressing a matrix of vectors with dimensions (n, 768) into a matrix with
dimensions (n, 300), while ensuring minimal loss of information. Initially, we attempted Principal Component
Analysis (PCA), a common technique for dimensionality reduction. However, we discovered that PCA
only effectively compressed the data when n was greater than 768, whereas our dataset often
involved smaller n values, typically less than or equal to 768. Subsequently, we explored Singular Value
Decomposition (SVD) as an alternative approach, but encountered similar limitations with n values.

After further research, we experimented with two other methods: random projection and averaging com-
pression. Random projection, a straightforward technique that projects data onto a lower-dimensional sub-
space using a random matrix, proved robust for dimensionality reduction, especially with small sample sizes.
However, quantifying the amount of preserved data with random projection posed challenges, although it could
be addressed using the Johnson-Lindenstrauss lemma. Additionally, we implemented a simpler averaging com-
pression method, dividing the original 768-dimensional vectors into equal-length segments and computing the
average of each segment to derive a lower-dimensional representation. However, neither of these methods
are expected to preserve as much data as PCA or SVD.

#### Doing Everything Ourselves
In the early stages of the project, we aimed to develop comprehensive solutions from scratch, intending to
extract descriptions from images and identify the most significant keywords and themes from these descriptions.
However, despite investing substantial time and effort into training our own models and seeking guidance
from a UMass ML professor, we encountered challenges in achieving meaningful semantic results. Recognizing the
limitations imposed by our timeframe, we concluded that leveraging pretrained models was essential for efficient
progress. Consequently, we opted to utilize existing pretrained models, such as Word2Vec and BERT, and
integrated the OpenAI API for obtaining image descriptions. While we may explore further fine-tuning or
even training our own models in the future, we prioritized using these established methods due to their
demonstrated effectiveness in delivering promising results, as evidenced in our project outcomes.

Furthermore, in our objective to compress our data using Word2Vec or other predefined embeddings, we
encountered another obstacle. While attempting to compress labels conveying general semantics, we discovered
that Word2Vec embeddings lacked contextual information from their surroundings, thus limiting their
effectiveness. This realization made us understand one of the primary motivations behind the use of attention
mechanisms for context transfer among tokens in natural language processing tasks. This prompted us to
explore alternative approaches for data compression, emphasizing the importance of context-aware embeddings
for preserving semantic meaning in our model’s representations - we even tried to create our own attention
based mechanism from scratch!

#### Pretrained Model Pains
In the development of our pre-trained model, we also encountered challenges when utilizing prompt engi-
neering to extract predefined attributes for image comparison. Despite our efforts to prompt GPT-4 to
strictly adhere to the specified attributes, we encountered difficulties as the model frequently injected or
replaced attributes not included in our predefined lists. Despite multiple attempts to guide GPT-4
through explicit prompts, we found that language prompting alone was insufficient to enforce adherence to our
attribute parameters. To address this issue, we devised a validation function to filter out any attributes
not included in our predefined list, replacing missing attributes with placeholders at the end of the list. This
approach effectively prioritized the predefined attributes used by GPT-4, as the attribute order is significant
for our comparison tasks. While this solution enables us to work with our predefined attributes, we
recognize the potential for alternative prompting strategies or further model tuning to ensure GPT-4 remains
within the specified parameter constraints, an area that requires further exploration and refinement from
our end.
