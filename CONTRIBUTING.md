
//asynchronously retrieve multiple documents
ApiFuture<QuerySnapshot> future =
    db.collection("cities").whereEqualTo("capital", true).get();
// future.get() blocks on response
List<QueryDocumentSnapshot> documents = future.get().getDocuments();
for (DocumentSnapshot document : documents) {
  System.out.println(document.getId() + " => " + document.toObject(City.class));
}RetrieveDataSnippets.java
