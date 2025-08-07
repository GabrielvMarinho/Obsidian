The process of separating a [[DataBase]] into pieces, [[Tech/Software/Tools/Kubernetes/Kubernetes Features/Horizontal Scaling|Horizontally Scaling]] It

Generally being a single shard in each different server.

The reason on why to shard is because of a necessity for scalability, what comes to mind is data size, however sharding can also make the query faster, since you will have a smaller dataset to write and read. So it's not only about data size, but also how many operations that collection/table is going through, even if the dataset is small.

