PROTOC_GEN_TS_PATH="../node_modules/.bin/protoc-gen-ts"
OUT_DIR="./ts"
PROTO_DIR="./proto"

protoc:
	protoc \
		-I$(PROTO_DIR)/ \
		--plugin="protoc-gen-ts=${PROTOC_GEN_TS_PATH}" \
		--js_out="import_style=commonjs,binary:${OUT_DIR}" \
		--ts_out="service=true:${OUT_DIR}" \
		$(PROTO_DIR)/*.proto