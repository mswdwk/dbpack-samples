
# Environment variables set when running the Go compiler.
GOOS ?= $(shell go env GOOS)
GOARCH ?= $(shell go env GOARCH)
GO_BUILD_ENVVARS = \
	GOOS=$(GOOS) \
	GOARCH=$(GOARCH) \
	CGO_ENABLED=0 

all: build-aggregation-svc build-order-svc build-product-svc
	
build-aggregation-svc:
	 CGO_ENABLED=0 go build -o aggregation_svc/AggregationSvc ./aggregation_svc

build-order-svc:
	 CGO_ENABLED=0 go build -o order_svc/OrderSvc ./order_svc

build-product-svc:
	 CGO_ENABLED=0 go build -o product_svc/ProductSvc ./product_svc

run:
	docker-compose -f docker-compose.yaml up --build -d
