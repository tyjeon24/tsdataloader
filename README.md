# tsdataloader
From database(PostgreSQL, ...) to PyTorch Dataloader.


```
from tsdataloader import PostgresDataLoader
from tsdataloader import PostgresDataset

dataset = PostgresDataset(
    db="your_dbname",
    user="your_user",
    password="your_password",
    host="localhost",
    port="5432",
    query="SELECT v1,v2 FROM my_table;",
    fetch_size=10000,
)

dataloader = PostgresDataLoader(dataset, batch_size=5)

for batch in dataloader:
    print(batch)

"""
tensor([[0.3642, 0.4362],
        [0.4080, 0.3847],
        [0.2716, 0.9373],
        [0.4719, 0.7099],
        [0.3831, 0.1706]])
tensor([[0.9456, 0.7972],
        [0.6847, 0.5980],
        [0.2215, 0.2913],
        [0.3048, 0.9703],
        [0.3780, 0.7710]])
...
"""
```