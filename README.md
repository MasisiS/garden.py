import spacy
nlp = spacy.load('en_core_web_sm')

gardenpathSentences = [
                      "They are forced to re-analyze the sentence",
                      "Mary gave the child a Band-Aid.",
                      "That Jill is never here hurts.",
                       ]
more_sentences = [
                 " Mary gave the child a Band-Aid."
                 "That Jill is never here hurts."
                 "The cotton clothing is made of grows in Mississippi."
                 ]                    

gardenpathSentences.extend(more_sentences)

for sentence in gardenpathSentences:
  texts = sentence.split()
  print(texts)

ner_categories = ["PERSON", "ORG", "GPE", "PRODUCT"]

emptystr = ""

# passing in a string 

for i in gardenpathSentences:

  emptystr += i

  print(emptystr)

doc = nlp(emptystr)
entities =[]

for ent in doc.ents:
  if ent.labe_ in ner_categories:
    entities.append((ent.text, ent.lable))
	
    for entity, category in entities:
      print(f"{entity}: {category}")
	
	
