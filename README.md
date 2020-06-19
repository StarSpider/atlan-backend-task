# atlan-challenge

Solution for Atlan Backend Engineering Internship Task

To build the RestAPI, run `docker-compose up --build` inside atlan-challenge directory.

Once the query completes or fails, the query is cancelled and the worker thread dies.

- If user pauses the update, the connection in that new thread is paused.
- If the user then clicks on resume, that connection can now be resumed.
- If user cancels, the connection will be destroyed, and then worker thread will be killed.
  (In such a case, the transaction will anyway be rolled back by the `nodejs-mysql` module, so partial update isn't an issue here)
- If the user does not pause, cancel or resume the transaction, and the query successfully completes, it will be committed to the database.

Hope to hear back from you soon!
Baibhav Ojha
