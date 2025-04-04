# Embedding model optimization

- Fine-tuning:
	Fine-tune on a relevant dataset
	Label data
- Contrastive learning:
	contrastive loss functions, triplet loss, NT-Xent
	focus on hard negatives
- Change the model:
	BERT, RoBERTa, cross-encoder models
- Dimensionality:
	Principal Component Analysis, t-SNE, L2 normalization
- Data augmentation, preprocessing:
	Remove noise, normalize text, and ensure consistency in tokenization

- How to measure the optimization effect:
	retrieval precision, recall, F1 score


# RAG optimization
- [Optimum Intel (Intel hardware only). Intel Neural Compressor in particular](https://github.com/huggingface/optimum-intel?tab=readme-ov-file)

- fastRAG (provokes conflicting dependencies in our project right now)

[Poetry](https://python-poetry.org/docs/basic-usage/) - library to potentially fix the conflicts.


## Fine-tuning
- Sentence transformers v3
- Dataset (must be compatible with the loss function)
- Loss function
- Training arguments
- Evaluator
- Trainer
	
	
## Sources:

https://huggingface.co/blog/train-sentence-transformers
https://vectorize.io/optimizing-embedding-model-performance-a-technical-approach-for-rag-pipelines/
https://huggingface.co/blog/intel-fast-embedding