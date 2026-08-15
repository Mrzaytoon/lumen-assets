# LUMEN assets

Binary frame-sequence packs downloaded on first run by the LUMEN hub.

Each `.lmpk` is one folder of PNG frames in a single container:

    "LMPK" | ver(1) | manifestLen(4, little endian) | manifest JSON | payload

The manifest is `{"f": folder, "v": 1, "e": [[name, offset, size], ...]}` with
offsets relative to the start of the payload. Nothing is base64'd - binary
survives HttpGet intact, so encoding it would cost a third of the transfer for
nothing.

These are render outputs, not source. They are here to be fetched by the hub.
