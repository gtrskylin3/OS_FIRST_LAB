# 1 этап
FROM gcc:13-bookworm AS builder
WORKDIR /app
COPY apps/backend ./apps/backend 
COPY lib ./lib 
COPY include ./include
RUN make -C lib 
RUN make -C apps/backend 

# 2 этап
FROM debian:bookworm-slim 
WORKDIR /app
COPY --from=builder /app/apps/backend/backend ./backend
CMD [ "./backend" ]
