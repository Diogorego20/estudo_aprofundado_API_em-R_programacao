
# Testes de Modelagem 3D com CadQuery

Este diretório faz parte do projeto **FabLab UFPB** e tem como objetivo documentar o uso da biblioteca **CadQuery** para modelagem paramétrica de peças 3D antes da impressão.

## 💡 Por que usar CadQuery?
CadQuery é uma biblioteca Python que permite criar modelos 3D de forma programável. Isso é útil para:
- Prototipagem rápida
- Testes de encaixe e medidas
- Geração de arquivos STL para impressão 3D
- Automatização de variações de modelos

## 🛠️ Instalação do CQ-editor
Para visualizar os modelos gerados com CadQuery:
1. Acesse o repositório oficial: [CadQuery GUI](https://github.com/CadQuery/CQ-editor)
2. Siga as instruções de instalação para seu sistema operacional.
3. Abra o CQ-editor e cole o código Python do modelo desejado.

## 📦 Exemplo de Código
```python
import cadquery as cq

# Medidas padrão
DIAMETRO_EXTERNO = 38
ALTURA_TOTAL = 110
DIAMETRO_ROSCA = 30

def criar_acionador(d_ext, altura, d_rosca):
    corpo_externo = cq.Workplane("XY").circle(d_ext / 2).extrude(altura)
    furo_interno = cq.Workplane("XY").circle(d_rosca / 2).extrude(altura)
    return corpo_externo.cut(furo_interno)

modelo = criar_acionador(DIAMETRO_EXTERNO, ALTURA_TOTAL, DIAMETRO_ROSCA)
show_object(modelo)
```

## 🖨️ Impressão 3D
Após validar o modelo no CQ-editor, você pode exportar o arquivo STL e enviá-lo para sua impressora 3D.

## 📁 Organização
Este diretório pode conter:
- Modelos `.py` com scripts CadQuery
- Arquivos `.stl` gerados
- Imagens de visualização
- Documentação técnica

---
FabLab UFPB - Laboratório de Fabricação Digital
