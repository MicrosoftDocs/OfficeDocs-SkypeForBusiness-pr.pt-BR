---
title: Interface do STU3 de integração do EHR e aplicativo pacientes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba como integrar registros de saúde eletrônicas ao aplicativo Microsoft Teams pacientes e à especificação de interface STU3.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e101f6ca50a76b4b8bb9d3dd33d35fd7706a81f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905743"
---
# <a name="stu3-interface-specification"></a>Especificação de interface STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar. O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Aguarde](#patient)
- [Observações](#observation)
- [Condição](#condition)
- [Encontrá](#encounter)
- [Allergy intolerância](#allergyintolerance)
- [Análise](#coverage)
- [Instrução medicação](#medication-request) (Substitui a MedicationOrder na versão DSTU2 do PatientsApp)
- Local (as informações necessárias deste recurso podem ser incluídas em encontrar)

> [!NOTE]
> O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado); No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.

As consultas do aplicativo Microsoft Teams pacientes para mais de um recurso deverão postar um pacote (lote) de solicitações para a URL do servidor FHIR. O servidor processará cada solicitação e devolverá um pacote dos recursos correspondentes a cada solicitação. Para obter mais informações e exemplos, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)consulte.

## <a name="capability-statement"></a>Declaração de recursos

Estes são os campos mínimos obrigatórios:

1. DEIXAR
   1. Modo
   2. Haja
   3. Recurso: tipo
   4. Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotar.)

Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="patient"></a>Aguarde

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de perfil do paciente do Argonaut:

1. Nome. fornecido
2. Nome. família
3. Sexo
4. DataDeNascimento
5. MRN (identificador)

Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

1. Name. Use
2. Name. Prefix
3. [GeneralPractitioner]-a referência GeneralPractitioner deve ser incluída no recurso de paciente (somente campo de exibição)

Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:

1. %
2. Family = (procura por todos os pacientes cujo nome de família contenha o valor)
3. especificado =\<subcadeia de caracteres>
4. DataDeNascimento = (correspondência exata)
5. Gênero = (valores sendo um dos sexo administrativos)
6. \_contagem (número máximo de resultados que devem ser retornados) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e \_da contagem que será usado pelo PatientsApp para limitar o número de registros retornados.
7. identificador =\<MRN>

O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:

- ID: essa é a ID do recurso que cada recurso no FHIR tem.
- MRN: esse é o identificador real do paciente que a equipe clínica saberia. Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR.
- Nome
- DataDeNascimento

Consulte o seguinte exemplo da chamada:

* * *

    Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: dadas = Ruth&Family = preto
    
    Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"relation": "self", "URL": <fhir-Server>/patient/_search "}]," entry ": [{" fullUrl ": <fhir-Server>/patient/<> de identificação do paciente", "recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "texto": {"status": "gerado", "div", "div": "<div>\n        <p>Ruth negro</p>\n      </div>"}," identificador ": [{" Use ":" usual "," tipo ": {" codificação ": [{" sistema ":"https://hl7.org/fhir/v2/0203"," código ":" Mr "," exibir ":" número do registro médico "," userselected ": false}]," texto ":" número do registro médico "," sistema ":http://hospital.smarthealthit.org" "," valor ":" 1234567 "}]," ativo ": verdadeiro," nome ": [{" usar ":" oficial "," família ":" preto "," fornecido ": [" Ruth "," C ",
    ]}], "telecomunicações": [{"System": "Phone", "value": "800-599-2739", "valor": "800-808-7785", "Use": "móvel", "valor": "", "Use": "celular", "valor" gênero ":" email "," valor ":" ruth.black@example.com "," ",", "gênero": "feminino", "DataDeNascimento": "1951-08-23", "endereço": [{"usar": "Home", "linha": ["26 South RdApt 22"], "cidade": "Sapulpa", "estado": "OK", "CEP": "74066", "país": "EUA"}]}, "localizar": {"Mode": "match"}}]}

* * *

    Solicitação: Obtenha o <fhir>/patient/<o ID do paciente>
    
    Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>", "identificador": [{"usar": "usual", "tipo": {"codificação": [{"sistema": "https://hl7.org/fhir/v2/0203", "código": "Sr",}], "texto": "número do registro médico"}, "valor": "1234567"}], "nome": [{"usar": "oficial", "família": "Adams", "determinado": ["Daniel", "X." ]}], "gênero": "macho", "Datadenascimentoe": "1925-12-23",}

* * *

Consulte [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="observation"></a>Observações

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil Argonaut de sinais essenciais](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Efetivo (data e hora ou ponto)
2. Code. Coding. Code
3. Valor de ValueQuantity. valor

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

1. Code. Coding. display
2. ValueQuantity. unidade

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<identificação do paciente>
2. _sort =-data
3. Categoria (consultaremos "category = Vital-Signs") para recuperar a lista de sinais essenciais.

Consulte este exemplo da chamada:

* * *

    Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<paciente-ID>&categoria = sinais essenciais
    
    Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "observação", "ID": "<Resource-ID>", "categoria": [{"codificação": [{"sistema": "https://hl7.org/fhir/observation-category", "código": "código vital" Code ": {" Coding ": [{" System ":"http://loinc.org"," código ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valor ": 72,0," unidade ":" {batidas}/min "," sistema ":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="condition"></a>Condição

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code. Coding [0]. Mostrar

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

1. AssertedDate
2. Gravidade

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<identificação do paciente>
2. _count =\<máximo de resultados>

Consulte o seguinte exemplo desta chamada:

* * *

    Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10
    
    Resposta: {"resourceType": "Bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "total": 2, "entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "código": {"codificação": [{"sistema": "http://snomed.info/sct", "código": "185903001", "exibição": "precisa de imunização influenza",}]}, "severidade": {"codificação": [{"sistema":http://snomed.info/sct"", "código": "24484000", "exibir": "severado}]}," assertedDate ":" 2018-04-04 "}},.
        .
        .
      ] }

* * *
Consulte [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="encounter"></a>Encontrá

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos "deve ter" o [perfil do núcleo dos EUA](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .

1. Situação
2. Digite [0]. Codificação [0]. Mostrar

Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil:

1. Período. início
2. Local [0]. Location. display

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<identificação do paciente>
2. _sort: desc =\<Field ex. Data>
3. _count =\<máximo de resultados>

O objetivo é poder recuperar o último local conhecido do paciente. Cada encontro faz referência a um recurso de localização. A referência também incluirá o campo de exibição do local.

Consulte [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code. Text
2. Code. Coding [0]. Mostrar
3. ClinicalStatus/VerificationStatus (Lemos)

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler o seguinte campo:

1. AssertedDate
2. Observação. texto
3. Reação
    1. Substância (um elemento de codificação)
    2. Manifestação (um elemento de codificação)

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. Paciente = \<identificação do paciente>

Consulte o seguinte exemplo da chamada: 

* * *

    Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente>
    
    Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1 "," entry ": [{" Resource ": {" resourceType ":" AllergyIntolerance "," ID ":" verificationStatus-ID> "," clinicalStatus ":" ativo "," ":" confirmado "," código ": {" codificação ", <" ":" confirmadohttp://rxnav.nlm.nih.gov/REST/Ndfrt"," código ": {" codificação ": N0000175503", "exibir": "sulfonamide Antibacterial",}], "texto": "sulfonamide Antibacterial"}, "assertedDate": "2018-01-01T00:00:00-07:00", "reação": [{"manifestação": [{"Coding": [{"http://snomed.info/sctSystem": "", "código": "271807003", "display": "Skin rash",}], "texto": "Skin rash"}],}]

* * *

Consulte [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="medication-request"></a>Solicitação de medicação

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil de solicitação principal do medicação-EUA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medicação. display (se referência)
2. Medicação. Text (se CodableConcept)
3. AuthoredOn
4. Solicitante. Agent. display

Além dos campos principais dos EUA, para uma ótima experiência do usuário, o aplicativo pacientes também pode ler os seguintes campos:

1. DosageInstruction[..]. Textos
2. Textos

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<identificação do paciente>
2. _count =\<máximo de resultados>

Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="coverage"></a>Análise

Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:

1. Agrupamento, pelo menos um elemento com
    1. GroupDisplay
    2. PlanDisplay
2. Período
3. Subscriberid

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. Paciente = \<identificação do paciente>

Consulte [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para obter outros detalhes sobre esse conjunto de campos.
