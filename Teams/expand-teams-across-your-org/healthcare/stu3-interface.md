---
title: Interface de integração STU3 App os pacientes e EHR
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integração de EHR app pacientes de equipes da Microsoft
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643062"
---
# <a name="stu3-interface-specification"></a>Especificação de interface de STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Configurando ou reconfigurando a um servidor FHIR para trabalhar com o aplicativo Microsoft equipes pacientes exige noções básicas sobre quais dados o aplicativo precisa acessar. O servidor FHIR deve oferecer suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Paciente](#patient)
- [Observação](#observation)
- [Condição](#condition)
- [Encontrar](#encounter)
- [Alergias Intolerance](#allergyintolerance)
- [Cobertura](#coverage)
- [Instrução remédios](#medication-request) (substitui o MedicationOrder na versão DSTU2 do PatientsApp)
- Local (as informações necessárias deste recurso pode ser incluídas na ocorrência)

> [!NOTE]
> O recurso de pacientes é o recurso obrigatório somente (sem que o aplicativo não será carregado nisso); No entanto, é recomendável que o parceiro implementar o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para uma melhor experiência do usuário final com o Microsoft equipes pacientes App.

Consultas do app pacientes de equipes da Microsoft para mais de um recurso devem lançar um pacote (em LOTES) de solicitações de URL do servidor FHIR. O servidor deverá processar cada solicitação e retornar um pacote dos recursos que correspondem a cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).

## <a name="capability-statement"></a>Instrução de recurso

Estes são os campos necessários mínimos:

1. REST
   1. Modo
   2. Interação
   3. Recurso: tipo
   4. [Extensão para OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html) de segurança:
2. FhirVersion (nosso código requer essa opção para entender qual versão podemos deve pivô.)

Consulte [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) para outros detalhes sobre este campo definido.

## <a name="patient"></a>Paciente

Aqui estão os campos necessários mínimos, que são um subconjunto dos campos perfil pacientes Argonaut:

1. Name.Given
2. Name.Family
3. Gênero
4. Data de nascimento
5. MRN (identificador)

Além dos [campos Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:

1. Name.Use
2. Name.Prefix
3. [GeneralPractitioner] - GeneralPractitioner a referência deve ser incluída no recurso paciente (somente para exibição field)

Uma pesquisa de recurso usa o método POST no /Patient/_search e os seguintes parâmetros:

1. ID
2. família = (pesquisas para todos os pacientes cujo nome família contém o valor)
3. determinado =\<substring>
4. Data de nascimento =(exact match)
5. Gênero = (valores sendo uma do gênero-administrativas)
6. \_Contagem de (número máximo de resultados que devem ser retornadas) <br> A resposta deve conter a contagem total de registros retornados como resultado de pesquisa e \_contagem será usada pelo PatientsApp para limitar o número de registros retornados.
7. identificador =\<mrn>

O objetivo é conseguir pesquisa e filtro do paciente pelo seguinte:

- ID: Este é o ID de recurso que tem de cada recurso no FHIR.
- MRN: Esse é o identificador real do paciente que seria saber a equipe de início de estudos clínicos. Podemos entender que este MRN baseia-se ao tipo de identificador de recurso identificador na FHIR.
- Nome
- Data de nascimento

Consulte o exemplo a seguir da chamada:

* * *

    Solicitação: Corpo da solicitação POST <fhir-server>/paciente/_search: determinado = ruth&family = preto
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "total": 1, "link": [{"relation": "self", "url": <fhir-server>/paciente/_search "}],"entry": [{ "fullUrl": <fhir-server>/paciente/<patient-id> ","recurso": {"resourceType":"Paciente","id":"<patient id>","meta": {"versionId":"1","lastUpdated":" 2017-10-18T18:32:37.000 + 00:00 "},"text": {"status":"gerado","div ": "<div>\n.        <p>Ruth preto</p>\n.      </div>"},"identificador": [{"usar":"normal","tipo": {"codificação": [{"sistema":"http://hl7.org/fhir/v2/0203","código":"MR","Exibir":"número de registro médico","userSelected": false}],"text":"número de registro médico"},"system":"http://hospital.smarthealthit.org","value":"1234567"}],"ativo": true," o nome": [{"usar":"oficial","família":"Preto","dado": ["Ruth","C."
    ]}], "telecomunicações": [{"sistema": "telefônicas", "value": "800-599-2739", "o uso": "residencial"}, {"sistema": "telefônicas", "value": "800-808-7785", "o uso": "mobile"}, {"sistema": "email", "value": "ruth.black@example.com"}], "gênero": "feminino", "data de nascimento": "1951-08-23", " endereço": [{"usar":"casa","linha": ["26 Sul RdApt 22"],"city":"Sapulpa","estado":"Okey","postalCode":"74066","country":"EUA"}]},"pesquisa": {"modo":"correspondência"}}]}

* * *

    Solicitação de: GET <fhir-server>/paciente/<patient-id>
    
    Resposta: {"resourceType": "Paciente", "id": "<patient id>", "identificador": [{"usar": "normal", "tipo": {"codificação": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR"}], "text": "número de registro médico"}, "value": "1234567"}], "nome": [{"usar": "oficial", " família":"Adams","dado": ["Daniel","X". {}]], "gênero": "masculino", "data de nascimento": "1925-12-23",}

* * *

Consulte [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) para outros detalhes sobre este campo definido.

## <a name="observation"></a>Observação

Esses são os campos necessários mínimos, que são um subconjunto do [perfil de Argonaut Vital-sinais](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Efetivo (data hora ou período)
2. Code.Coding.Code
3. ValueQuantity.Value

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:

1. Code.Coding.Display
2. ValueQuantity.Unit

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. Data = _sort
3. categoria (podemos irá consultar "category = sinais de vital") para recuperar a lista de sinais de vital.

Consulte este exemplo da chamada:

* * *

    Solicitação: Obtenha <fhir-server>/Observação? paciente = <patient-id>&category = vital-sinais
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recurso": {"resourceType": "Observação", "id": "<resource id>", "categoria": [{"codificação": [{"sistema": "http://hl7.org/fhir/observation-category", "código": " vital-sinais de"}]}],"código": {"codificação": [{"sistema":"http://loinc.org","código":"8867-4","exibição":"heart_rate"}]},"effectiveDateTime":" 2009-04-08T00:00:00-06:00 ","valueQuantity": {"value": 72.0,"unidade":" {batidas} / min ","sistema":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Consulte [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) para outros detalhes sobre este campo definido.

## <a name="condition"></a>Condição

Eis os campos necessários mínimos, que são um subconjunto do [perfil de condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code.Coding[0]. Exibição

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:

1. AssertedDate
2. Severidade

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. Count =\<results> max

Consulte o exemplo a seguir desta chamada:

* * *

    Solicitação: Obtenha <fhir-server>/condição? paciente = <patient-id>&_count = 10
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": dia 2, "entry": [{"recurso": {"resourceType": "Condição", "id": "<resource id>", "código": {"codificação": [{"sistema": "http://snomed.info/sct", "código": "185903001", " Exibir":"Necessidades vacina de influenza,"}]},"gravidade": {"codificação": [{"sistema":"http://snomed.info/sct","código":"24484000","Exibir":"Grave"}]},"assertedDate":"2018-04-04"}},.
        .
        .
      ] }

* * *
Consulte [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) para outros detalhes sobre este campo definido.

## <a name="encounter"></a>Encontrar

Esses são os campos necessários mínimos, que são um subconjunto dos campos [perfil encontrar de núcleo dos EUA](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "deve ter").

1. Status
2. Tipo [0]. Codificação [0]. Exibição

Além disso, os seguintes campos do perfil nos encontrar Core "devem suportar" campos:

1. Period.Start
2. Local [0]. Location.Display

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. _sort:desc =\<campo ex. date>
3. Count =\<results> max

O objetivo é conseguir recuperar local conhecido do último do paciente. Cada ocorrência faz referência a um recurso local. A referência também deverá incluir o campo de exibição do local.

Consulte [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) para outros detalhes sobre este campo definido.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos necessários mínimos, que são um subconjunto do perfil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code.Text
2. Code.Coding[0]. Exibição
3. ClinicalStatus/VerificationStatus (Lemos ambos)

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler o campo a seguir:

1. AssertedDate
2. Note.Text
3. Reação
    1. Substância (um elemento de codificação)
    2. Manifestação (um elemento de codificação)

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. Paciente = \<id> paciente

Consulte o exemplo a seguir da chamada: 

* * *

    Solicitação: Obtenha <fhir-server>/AllergyIntolerance? paciente = <patient-id>
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "clinicalStatus": "ativo", "ve rificationStatus":"confirmado","código": {"codificação": [{"sistema":"http://rxnav.nlm.nih.gov/REST/Ndfrt","código":"N0000175503","Exibir":"sulfonamide antibacterial,"}],"text":"ant de sulfonamide ibacterial"}"assertedDate":" 2018-01-01T00:00:00-07:00 ","reação": [{"manifestação": [{"codificação": [{"sistema":"http://snomed.info/sct","código":  "271807003", "Exibir": "explosão de capa,"}], "text": "explosão capa"}],}]}}]}

* * *

Consulte [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) para outros detalhes sobre este campo definido.

## <a name="medication-request"></a>Solicitação de remédios

Estes são os campos necessários mínimos, que são um subconjunto dos [EUA Core remédios solicitar perfil](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medication.Display (se referência)
2. Medication.Text (se CodableConcept)
3. AuthoredOn
4. Requester.Agent.Display

Além dos campos nos principais, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:

1. DosageInstruction [..]. Texto
2. Texto

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. Count =\<results> max

Consulte [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) para outros detalhes sobre este campo definido.

## <a name="coverage"></a>Cobertura

Estes são os campos necessários mínimos, não cobertos por nós principais ou Argonaut perfis:

1. Agrupamento, pelo menos um elemento com
    1. GroupDisplay
    2. PlanDisplay
2. Período
3. SubscriberId

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. Paciente = \<id> paciente

Consulte [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) para outros detalhes sobre este campo definido.
