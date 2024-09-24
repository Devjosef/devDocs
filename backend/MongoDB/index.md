# MongoDB

## Introduction
MongoDB is a document-oriented NoSQL database used for high volume data storage. It uses JSON-like documents with optional schemas.

## Basic Syntax
```javascript
// Example of a basic MongoDB connection using Mongoose
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost:27017/mydatabase', {
    useNewUrlParser: true,
    useUnifiedTopology: true,
});

const db = mongoose.connection;
db.on('error', console.error.bind(console, 'connection error:'));
db.once('open', function() {
    console.log('Connected to MongoDB');
});
```

## Common Use Cases
- Storing large volumes of data
- Real-time analytics
- Content management systems
- Internet of Things (IoT) applications

## Advanced Features
- **Aggregation Framework**: Perform complex data processing and transformations.
- **Sharding**: Distribute data across multiple machines.
- **Replication**: Ensure high availability and data redundancy.
- **Indexing**: Improve query performance with various types of indexes.

## Code Snippets
### Aggregation Framework
```javascript
// Example of an aggregation pipeline
const pipeline = [
    { $match: { status: 'A' } },
    { $group: { _id: '$cust_id', total: { $sum: '$amount' } } },
    { $sort: { total: -1 } },
];

db.collection('orders').aggregate(pipeline).toArray((err, result) => {
    if (err) throw err;
    console.log(result);
});
```

### Sharding
```javascript
// Enable sharding for a database
sh.enableSharding('mydatabase');

// Shard a collection
sh.shardCollection('mydatabase.mycollection', { _id: 1 });
```

### Replication
```javascript
// Initialize a replica set
rs.initiate({
    _id: 'rs0',
    members: [
        { _id: 0, host: 'localhost:27017' },
        { _id: 1, host: 'localhost:27018' },
        { _id: 2, host: 'localhost:27019' },
    ],
});
```

### Indexing
```javascript
// Create an index on a collection
db.collection('users').createIndex({ email: 1 }, { unique: true });
```

## Tips & Best Practices
- **Schema Design**: Design schemas according to your application's access patterns.
- **Indexing**: Use indexes to improve query performance but be mindful of write performance.
- **Backup and Restore**: Regularly backup your data and test your restore process.
- **Monitoring**: Monitor your MongoDB instances for performance and health.
- **Security**: Use authentication, authorization, and encryption to secure your data.

## External Resources
- [MongoDB Official Documentation](https://docs.mongodb.com/)
- [Mongoose Documentation](https://mongoosejs.com/docs/guide.html)
- [MongoDB University](https://university.mongodb.com/)
- [Awesome MongoDB](https://github.com/ramnes/awesome-mongodb)