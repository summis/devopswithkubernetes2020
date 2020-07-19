FROM rust:1.44-alpine

# cargo command fetches automatically my project from github and
# puts final binary to /usr/bin
RUN cargo install --git https://github.com/summis/rust-string-outputter.git  --root /usr

CMD ["rust-string-outputter"]
