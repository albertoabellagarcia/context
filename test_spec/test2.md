test
====

# encabezado españa camión
<p>La dirección postal.</p>

## encabezado españa camión
<p>Un nombre alternativo para este artículo</p>

### encabezado españa camión
<p>El nombre de este artículo.</p>

#### encabezado españa camión
<p>Factor de potencia de desplazamiento para cada fase. La cantidad se basa en la frecuencia fundamental del sistema. Los valores reales serán transmitidos por una subpropiedad por cada fase de corriente alterna: L1, L2 y L3</p>

##### encabezado españa camión
<p>Tensión entre fases. Un valor para cada par de fases: fases 1 y 2 (L12), fases 2 y 3 (L32), fases 3 y 1 (L31).</p>

###### encabezado españa camión
<p>Factor de potencia para cada fase. Los valores reales serán transmitidos por una subpropiedad por cada fase de corriente alterna: L1, L2 y L3</p>
encabezado españa camión<p>El voltaje entre cada fase y el conductor neutro. Los valores reales serán transmitidos por una subpropiedad por cada fase de corriente alterna: L1, L2 y L3</p>
encabezado españa camión<p>Debe ser igual a "Medición en tres fases".</p>
and this is  **a bold text**  I am afraid 
and this is  ** `a bold and monospaced text` ** I am afraid
and this is 

```

languages = ["ES"]
authKey = "e1ee24ce-f9f1-e664-27a4-82a6606bf8dc"
for lang in languages:
    for sentence in text:
        esSentence = translation(sentence, "EN", lang, authKey)
        print(type(esSentence))
        print(esSentence)
        mdFile.new_line(str(esSentence))
        # print(chardet.detect(esSentence))
print(mdFile)
mdFile.create_md_file()
```
a piece of code 
and this is 

```yaml

Animal:
  description: 'An observation of animal conditions at a certain place and time. This data model has been developed for the IoF2020 UC ShareBeef by UCO and SensoWave.'
  properties:
    address:
      properties:
        addressCountry:
          type: string
        addressLocality:
          type: string
        addressRegion:
          type: string```
