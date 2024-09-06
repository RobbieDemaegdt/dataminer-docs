---
uid: Protocol.Params.Param.Interprete.DefaultValue
---

# DefaultValue element

Specifies the default value to be assigned to the parameter if it is empty after startup.

## Type

string

## Parent

[Interprete](xref:Protocol.Params.Param.Interprete)

## Remarks

*Feature introduced in DataMiner 8.5.3 (RN 8776).*

## Examples

```xml
<Interprete>
	<RawType>other</RawType>
	<LengthType>next param</LengthType>
	<Type>string</Type>
	<DefaultValue>This is the default value</DefaultValue>
</Interprete>
```

> [!NOTE]
> Default values can only be assigned to standalone parameters. They do not work for table columns.

> [!NOTE]
> Do not use DefaultValue tags to fill in an Exception value.
> Exceptions should be used after the logic of the driver has run.
> After polling for example, you will either have a value or fill in an exception value saying: Not Available, Not Applicable, ...
> Do not try to use DefaultValue + Exceptions to mask "Not Initialized" parameters! A parameter with "Not Initialized" is normal right after startup. It just shouldn't remain on Not Initialized after polling cycles & logic has finished.
>
> There is an exception to this rule: If you're dealing with Parameters that do not get their data from a device, but are simply used for internal configuration it could be than you want these parameters to start on the 'exception' value. 
