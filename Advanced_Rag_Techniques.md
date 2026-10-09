
## MultiModel Rag System :



Multimodal AI refers to systems that can understand and combine multiple types of data — such as text, images, audio, and documents — within a single workflow.
A single PDF might contain paragraphs, images, tables, and diagrams, all of which contribute to the overall meaning.


At a basic level, a multimodal implementation might involve sending both text and an image to a vision-capable model, allowing it to interpret visual content alongside a user’s query. This simple pattern forms the foundation for more advanced systems, where multiple data types are processed, stored, and retrieved together to generate richer and more accurate AI responses.





## Latency:

we have testing code by simply adding latency code i can calculate latency for different levels, retrievel or generation.






Langchain is like a glue that combine different components together through a simple pipeline like connecting database, LLM's with Rag pipeline. else we need to create separate function to combine these components together.



================================================================
## TOKEN COST
https://www.digitalocean.com/resources/articles/llm-cost-calculation-guide


LLM costs depend on more than token pricing. Input and output tokens, context windows, caching, batch processing, and tool usage all contribute to your final inference bill.

Estimating request costs before deployment, plus optimizing prompts, batching, model routing, and response length, can help reduce AI spending without affecting output quality.

Monitor request-level metrics, attribute costs to applications and teams, and track efficiency metrics such as cost per request and cost per successful task to keep production AI workloads within budget


================================================================

llm cost is calculated based on per million token and each llm provider have their different ways or api's to calculate llm cost for some llm's reasoning also part of the total cost.
i want to calculate llm cost for my project, like how much cost it takes during conversation for that The formula: cost = (input tokens ÷ 1,000,000 × input price) + (output tokens ÷ 1,000,000 × output price).    So can you make me clear for 2 things,  1st what ideal cost(price) should i consider for input and output tokens and secondly how can i calculate input and output tokens.




I have used Groq api key with open-ai 120 parameter model, name "openai/gpt-oss-120b" .
These are some open weight models provided by some third party providers. like openai model and api is provided by groq .


========================================================================================================


There is some limitations as well with langchain like we can't use some specific fuctions in diffrent langchain tools which works well without langchain like calculating token used in llm and i tried to impliment local weight embedding model hugging face which does not required any api cost then i have use specific type hf to use with langchain.


=================================================================================================================

## Semantic Chunking :

If you remember only one thing:

Semantic chunking looks for places where the meaning/topic of the text changes significantly, and uses those changes as chunk boundaries.

So instead of saying:

"Create a chunk every 500 tokens"

you're effectively saying:

"Keep adding text while the semantic topic remains coherent; when the topic changes significantly, start a new chunk."

For your RAG project, I'd actually recommend not using pure semantic chunking blindly. A strong approach is usually "structure-aware + semantic chunking + min/max token limits", because semantic chunking alone can sometimes create chunks that are either too tiny or unexpectedly huge.


It increases latency with embedding cost.






------------------------------------------------------------------------------------------------------------------------------------------------------
## Reranking
(Suppose you retrieved top 3 chunks but relevant information is present in 5th or below chunks then what you will do?)

(Reranking is the technique to optimize the retrieval quality )
Document chunks converted into embeddings(through cross-encoders) and stored into vector database.
When user passes query then most similar chunks will retrieved from vector database by applying similarity search between vectors.

Reranker assign ranks to each chunks using Bi-encoder so that we can choose chunks which have higher rank from all of those chunks.
This will help to reduce llm cost but no need to apply until there is higher need because it consume lot of latency.
Re-ranker uses Bi-encoder internally for assigning rank

In my scenario i'm going through the problem of token limit because of my open source chat_groq model which provides 7000 token per minute and if i passes huge number of retrieved chunks then i got 429 error.


(What is encoder, Cross-encoder and Bi-encoder?) (what is HNSW index during creation of faiss index)


cross-encoder and bi-encoder both are embedding models.
Bi-Encoder : Here we passes query and documents separately and it generates embeddings only, then perform vector operations for similarity.
Cross-Encoder : Here Cross-Encoder processes the query and document together and we get some relevance score as the final output. Cross-Encoders are generally better at understanding the relationship between a specific query and a specific document. It does't store anything.

Both internally uses attention mechanism.
if you want 5% increase of recall with cost of 50x higher latency.  # 9.5 sec vs 528 sec in benchmark

Interview-ready answer

If an interviewer asks:
"What's the difference between a bi-encoder and cross-encoder?"

You can say:
A bi-encoder independently converts the query and documents into embeddings, allowing efficient similarity search using vector databases such as FAISS. A cross-encoder takes the query and document together and directly predicts their relevance score. Cross-encoders are generally more accurate for ranking but computationally more expensive, so in RAG systems we commonly use a bi-encoder for initial retrieval and a cross-encoder for reranking the top-K results.


(How Embeddings of any text is generated internally and how cross encoder model works internally)
(when to use or not use reranker model)



Like llm context window increased so far then it is possible to pass all chunks together for response generation but it increases llm cost so far. If recall is more important then latency or llm cost is also important in that cases we can go with reranking,


============================================================================================================================================================
## Evaluation Metrices

AnswerRelevancyMetric -
    It does't care weather the answer is taken from retrieval or not it care about weather generated answer relevant to user's question. It measures relevance score between actual and generated answer.


2. FaithfulnessMetric -
    It does't care weather the answer factually correct of not but it should be from retrieval.


3. ContextualPrecisionMetric -
 





Remember
     First check Recall, is retriever able to retrieve all relevant information required to answer then check  Precision value that helps to identify weather most relevant chunks are at the top or not if it is lower in that case we think to go towards reranking .


if recall is low in that sense we need to check by increasing top k values still recall is not improved (Like there is complete information related to user query but not exact same that user want ) in that sense retrieval has problem we need to change technique like BM25 etc.

if recall is improved by top-k but precision is low that means most relevant information is not at the top in that case we have to go towards reranking .
