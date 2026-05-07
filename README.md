# utherverse.vww
decompiling communications between utherverse client and server via port 4990

# Resolution
Client communicates with ```http://www.utherverse.com/DNSResolve.aspx?type=A&query=utherverse.vww``` and it gets XML back

```
<DNSLookup version="1">
  <question type="A" query="utherverse.vww" />
  <answer status="success">
    <record type="A" value="54.39.167.199" />
  </answer>
</DNSLookup>
```

Subsequent communications to port 4990 occur with ```54.39.167.199```

# Protocol Format

```
32-bit length, little endian length of data
6-bytes packet-type
...data...
```

# packet-type 04 00 00 00 00 00

Packet is first out the door and complete randomness every time.

Used in seeding encryption for subsequent requests.
