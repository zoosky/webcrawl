         

        curl -i -XPOST \                                                                
        -d '{"url": "https://www.example.com", "throttle": 100}' \
            http://localhost:8000/api/crawl
        HTTP/1.1 200 OK
        content-type: application/json
        content-length: 32
        date: Tue, 04 Aug 2020 15:26:46 GMT

        {"id":"https://www.example.com"}%      

        curl -i -XPOST  -d '{"url": "https://www.kapp.technology", "throttle": 50}' http://localhost:8000/api/crawl

        curl -i -XGET http://localhost:8000/api/results\?id\=https://www.example.com 
        curl -i -XGET http://localhost:8000/api/results/count?id\=https://www.example.com
        curl -i -XGET http://localhost:8000/api/domains

       curl -i -XGET http://localhost:8000/api/domains
                                                                   
        HTTP/1.1 200 OK
        content-type: application/json
        content-length: 83
        date: Tue, 04 Aug 2020 15:39:44 GMT

        ["https://kapp.technology","https://www.example.com","https://www.kapp.technology"]%  

        curl -i -XGET http://localhost:8000/api/results\?id\=https://kapp.technology