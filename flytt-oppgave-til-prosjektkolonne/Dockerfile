FROM clux/muslrust@sha256:1377dd0e05d5849c8aa12b43ec3adc2401c4073e29230b77f4489364dc8341fc as build
COPY assign-gh-item-to-project-field .
RUN cargo build --release --target x86_64-unknown-linux-musl

FROM scratch
#RUN mkdir /bin
#WORKDIR /bin
COPY --from=build /volume/target/x86_64-unknown-linux-musl/release/assign-gh-item-to-project-field .
ENTRYPOINT ["/assign-gh-item-to-project-field"]
CMD ["--help"]
