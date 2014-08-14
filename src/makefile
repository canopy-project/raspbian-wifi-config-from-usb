TARGET := raspbian-wifi-config-from-usb
.PHONY: default
default: $(TARGET)

SOURCE_FILES := rwcfu.c

INCLUDE_FLAGS :=

$(TARGET) : $(SOURCE_FILES)
	gcc $(SOURCE_FILES) -std=gnu99 -g $(INCLUDE_FLAGS) -lcanopy -lcurl -lwebsockets -lrt -o $@

.PHONY: install
install:
	cp $(TARGET) /usr/local/bin
