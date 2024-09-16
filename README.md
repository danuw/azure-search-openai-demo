CopiLAWt
=====

This is our entry for the https://github.com/microsoft/RAG_Hack at https://github.com/microsoft/RAG_Hack/issues/110

> This is a repo based on the original sample available at https://github.com/Azure-Samples/azure-search-openai-demo

## To run...

First make sure you are logging to the correct azure tenant:

```sh
az login
```

and then following the steps here https://github.com/Azure-Samples/azure-search-openai-demo?tab=readme-ov-file#deploying that start with `azd auth login` assuming you have the [pre-requisites tools listed here](https://github.com/Azure-Samples/azure-search-openai-demo?tab=readme-ov-file#local-environment).

We have mainly been testing with the `Ask a question` tab. In there, open the developer settings and ensure you are happy with the prompt (you can always play and adjust later). Also, change the number of search results to at least 10.

Once deployed, start asking questions, checking the reference documents and tweaking your request(s) to make it more and more efficient at bringing what you want straight away.

## Options

### More test data
[Documents we have added](data/SampleWills) are free samples available online as well as wills generated using OpenAI/ChatGPT to ensure we had more test data.

You can then run `./scripts/prepdocs.sh` to upload and reindex.

### Additional settings

As described in [docs/deploy_lowcost.md](docs/deploy_lowcost.md), you deploy a more economical solution for testing, but beware of the limitations listed below.


## Example prompts

Here are some example prompts we used to test. 

Do we have any will where inheritance goes to a charity?
What is the will where the beneficiaries get the most money?
What is the will where the Worthington Foundation get the biggest share of the inheritance?
Do we have any wills where children are the only beneficiaries?
Do we have any wills where there are more than one child ? 
Do we have any wills where there are many children ?
Do we have any wills where beneficiaries are animals?
Do we have any wills where property is held in trust for a certain amount of time?
Do we have any wills where property is held in trust for a certain amount of time for beneficiaries under 25?

While some worked straight away, some returned slightly different results at times and others some server errors we have not yet had a chance to investigate, but that will hopefully come through further updates soon...

This repo was only intended for demo purposes and only scratches the surface of is possible or would be required to go to production, though results looks very promising and would be great to try on a real knowledge base.

## Finally

1. Demo [on youtube](https://www.youtube.com/playlist?list=PL5_O2kt-UsIVjINtl_oH4VJ3FjlaoBbHp)


2. Experience with RAG?

- Loads of boiler plate solutions to focus on use case as opposed to technology (what instead of how)
- Powerful combination of Azure AI search for indexing with RAG to harness quality results very quickly with very little tweaks


3. Why this is needed ?

- Lawyers and legal professionals spend a great deal of time on legal research.
- This includes researching similar or closely related cases.
- However, this low value-added work is rarely billed to the client, despite the time it represents.
- As part of this project, we focused on a specific use case: will research. The tool we've developed enables users to use a natural language search to find examples of wills that meet specific criteria expressed in natural language.
- The aim is to save time for the legal professions, enabling them to focus on the real added value of their profession.


4. How did RAG help us build this solution?

- While usual Gen AI chat bots can provide interesting response though they tend to hallucinate/make things up!
- Normal search is based on keywords and still requires a significant effort to ensure a result’s relevance.
- RAG allows our solution to be based on relevant company  information securely, with links to source documentation, where GenAI can provide a response based on meaning (as opposed to keywords!) in a flash

