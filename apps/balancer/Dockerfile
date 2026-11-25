# 1 этап
FROM gcc:13-bookworm AS builder
WORKDIR /app
COPY apps/balancer ./apps/balancer
COPY lib ./lib 
COPY include ./include
RUN make -C lib 
RUN make -C apps/balancer  

# 2 этап
FROM debian:bookworm-slim 
WORKDIR /app
COPY --from=builder /app/apps/balancer/balancer ./balancer
CMD [ "./balancer" ]
