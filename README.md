# pl_phon
**Finding words with foreign pronunciation in Polish.**

In order to train and use an ASR (Automatic Speech Recognition) system, many components are required, among them - a pronunciation model. A simplest form of a pronunciation model is a dictionary of pronunciations, consisting of words in a given language and their pronunciations.

Such dictionaries can be prepared by hand, using rule-based grammars or a trained model, generating pronunciations. The latter two cases are of course much more time- and cost-effective, they may however introduce some errors. A common source of such error may be a word with "non-native" pronunciation used in a language - often a name of a person or a product, sometimes inflected using morphological rules of the studied language.

Words such as *googlowałam*, *facebook* or *Williamów* can serve as tricky examples in Polish. A simple pronunciation model may fail to provide correct pronunciation for such tokens, introducing error to the dataset. To avoid that, a "non-native" word detection model can be used, to find words requiring attention, for inspection of engineers or data annotators.

**The type of the problem is binary classification (native vs non-native pronunciation, or in this case - Polish vs non-Polish), as further division into source languages is not necessary.**

As is presented in the project notebook, general-use state-of-the-art language detection models do not provide the information necessary in this case. When given examples listed above, they (correctly) identify *googlowałam* and *Williamów* as Polish words, not accounting for the "non-native" pronunciation.

For this reason, after basic tests, the author decided to attempt to create own solution.
