FROM gcc:13-bookworm AS builder
WORKDIR /app 
COPY include ./include 
COPY lib ./lib
COPY apps/loadgen ./apps/loadgen 
RUN make -C lib 
RUN make -C apps/loadgen 

FROM debian:bookworm-slim 
WORKDIR /app 
COPY --from=builder app/apps/loadgen/loadgen ./loadgen
CMD ["./loadgen"]