# Testing the zipkin plugin:

Run cassandra and postgres locally.

    docker run -it -p 15002:9000 -p 15003:9001 moul/grpcbin
    docker run -p 9411:9411 -it openzipkin/zipkin:2.19

    KONG_SPEC_TEST_GRPCBIN_PORT=15002 \
    KONG_SPEC_TEST_GRPCBIN_SSL_PORT=15003 \
    bin/busted -o gtest spec/03-plugins/34-zipkin/
