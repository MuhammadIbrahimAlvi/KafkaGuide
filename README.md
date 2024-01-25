# KafkaGuide
1.) <b> Kafka Topics </b> <br/>
Topics are the particular stream of data without any constraints unlike in database. You can have as many Topics as you want inside of your cluster and can have as many Topics as you want inside of your cluster. You can store Kafka Topics in any format like json, avro schema etc. You cannot query to access the data from the Kafka but you need Producers to send data and Consumers to read. <br/>
2.) <b> Kafka Partitions and Offsets </b> <br/>
Topics are split into <b><ins>Partitions</ins></b>. 
<ul>
<li>
  Messages in each Partitions are ordered.
</li>
  <li>
    Each message within the idea gets an incremental id called <b><ins>Offsets.</ins></b>
  </li>
  <li>
    Kafka Topics are immutable means once the data is written inside of the Partition it cannot be modified.
  </li>
</ul>
<img width="950" alt="Screenshot 2024-01-10 at 7 02 43 PM" src="https://github.com/MuhammadIbrahimAlvi/KafkaGuide/assets/65025980/0ed83dd3-7d62-4b1c-8bbc-ef3c5c32871d">

### Important Points: <br/>
<ol>
  <li>
    Data is only kept for limited time (One week - configurable).
  </li>
  <li>
    Offset only have a meaning for a specific partition. <br/>
    <ul>
      <li>Offset 3 in the Partition 0 doesn't have the same data as of the Offset 3 of Partition 1.</li>
      <li>Offsets are not reused even if the previous messages have been deleted.</li>
    </ul>
  </li>
  <li>
    Order is guaranteed only within a Partition(not across Partitions).
  </li>
  <li>
    Data is assigned randomly to a Partition unless the key is provided.
  </li>
  <li>
    You can have as many Partitions as you want as per Topic.
  </li>
</ol>
3.) <b> Kafka Producers </b> <br/>
<ul>
<li>
  Messages in each Partitions are ordered.
</li>
  <li>
    Producers write data to the Topics (which are made up of partitions).
  </li>
  <li>
    Producers know to which partition to write to (and which Kafka broker has it).
  </li>
    <li>
    In case of Kafka broker failures, Producers will automatically recover.
  </li>
</ul>

<img width="974" alt="image" src="https://github.com/MuhammadIbrahimAlvi/KafkaGuide/assets/65025980/d2f33272-09b6-4bb3-979e-9a065b24ef38">



