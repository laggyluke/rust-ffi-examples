ifeq ($(shell uname),Darwin)
    EXT := dylib
else
    EXT := so
endif

all: target/libdouble_input.so
	ruby src/main.rb

target/libdouble_input.so: src/lib.rs Cargo.toml
	cargo build
	(cd target && ln -nsf debug/libdouble_input-*$(EXT) libdouble_input.so)

clean:
	rm -rf target
