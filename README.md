# Running the MongoDB Assignment Code

This README provides step-by-step instructions on how to set up and run the provided MongoDB scripts (`insert_books.js` and `queries.js`) for the PLP Bookstore assignment. These scripts handle data insertion and various queries on a MongoDB database.

## Prerequisites
- **MongoDB Installation**: 
  - Install MongoDB Community Edition on your local machine (download from [mongodb.com](https://www.mongodb.com/try/download/community)) OR create a free MongoDB Atlas cluster (sign up at [atlas.mongodb.com](https://www.mongodb.com/atlas/database)).
- **MongoDB Shell (mongosh)**: This comes bundled with MongoDB installation. Use it to interact with the database.
- **Optional Tools**:
  - MongoDB Compass: A GUI tool for visualizing your database (download from [mongodb.com/products/compass](https://www.mongodb.com/products/tools/compass)).
  - Node.js: Not required, as these are plain JavaScript files runnable in mongosh.

Ensure the `insert_books.js` and `queries.js` files are saved in your working directory.

## Setup Steps

1. **Start MongoDB**:
   - For local installation: Run `mongod` in a terminal to start the MongoDB server (default port: 27017).
   - For Atlas: No server start needed; use the connection string provided in your Atlas dashboard.

2. **Connect to MongoDB**:
   - Open a new terminal and run `mongosh` (or `mongo` if using an older version).
   - For local: Simply type `mongosh`.
   - For Atlas: Use `mongosh "mongodb+srv://<username>:<password>@<cluster-url>/plp_bookstore?retryWrites=true&w=majority"` (replace placeholders with your Atlas credentials).

3. **Create the Database**:
   - In mongosh, run: `use plp_bookstore`
   - This switches to (or creates) the `plp_bookstore` database.

## Running the Code

### Run Queries (`queries.js`)
1. Ensure `queries.js` is in your current directory.
2. You have two options:
   - **Run individually**: Copy-paste queries one by one from `queries.js` into mongosh and press Enter. This is recommended since the code contains a delete operation.
3. Example outputs:
   - Queries will print results directly in the shell (e.g., documents matching a find operation).
   - Aggregation pipelines return computed results like averages or counts.

## Viewing Data (for Screenshot)
- **Using MongoDB Compass**:
  1. Open Compass and connect using your local (`mongodb://localhost:27017`) or Atlas connection string.
  2. Navigate to `plp_bookstore` > `books`.
  3. View documents; take a screenshot showing the collection and sample data.
- **Using Atlas Web UI**:
  1. Log in to Atlas, go to your cluster > "Database" > `plp_bookstore` > `books`.
  2. View documents in the "Find" tab; screenshot the page.

## Troubleshooting
- **File Not Found**: Ensure files are in the directory mongosh is running from, or use absolute paths (e.g., `load("/path/to/insert_books.js")`).
- **Connection Issues**: Check firewall/port for local, or whitelist IP in Atlas.
- **Errors in Scripts**: Ensure valid JavaScript syntax; mongosh will show errors.
- **Cleanup**: To reset, run `db.books.drop()` to delete the collection.
- **Versions**: Tested with MongoDB 6+ and mongosh 1+.

## Additional Notes
- These scripts demonstrate CRUD, advanced queries, aggregations, and indexing as per the assignment.
- For production, consider error handling and security (e.g., authentication).
- If modifying scripts, save changes and reload.

For questions, refer to MongoDB docs: [docs.mongodb.com](https://docs.mongodb.com/).
