---
title: " Interface de integração DSTU2 App os pacientes e EHR"
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
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643060"
---
# <a name="dstu2-interface-specification"></a>Especificação de interface de DSTU2

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Configurando ou reconfigurando a um servidor FHIR para trabalhar com o aplicativo Microsoft equipes pacientes exige noções básicas sobre quais dados o aplicativo precisa acessar. O servidor FHIR deve oferecer suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Paciente](#patient)
- [Observação](#observation)
- [Condição](#condition)
- [Encontrar](#encounter)
- [Intolerance alergia](#allergyintolerance)
- [Cobertura](#coverage)
- [Ordem de remédios](#medication-order)
- [Local](#location)

> [!NOTE]
> O recurso de pacientes é o obrigatório somente (sem que o aplicativo não será carregado nisso. No entanto, é recomendável que o parceiro implementar o suporte para todos os recursos mencionados acima por especificações fornecidas abaixo para uma melhor experiência do usuário final com o Microsoft equipes pacientes App.

Consultas do app pacientes de equipes da Microsoft para mais de um recurso postagem um pacote (em LOTES) de solicitações de URL do servidor FHIR. O servidor processa cada solicitação e retorna um pacote dos recursos que correspondem a cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).

Os seguintes recursos FHIR devem ser acessados pela referência direta de recursos.

## <a name="conformance-minimum-required-field-set"></a>Definir campo obrigatório mínimo de conformidade

 O servidor FHIR deve implementar a declaração de conformidade de ter um resumo reais dos seus recursos. Esperamos que os parâmetros em um servidor de FHIR DSTU2 abaixo:

1. REST
   1. Modo
   2. Interação
   3. Recurso: tipo
   4. [Extensão para OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html) de segurança:
2. FhirVersion (nosso código requer essa opção para entender qual versão podemos deve pivô conforme oferecemos suporte para várias versões.)

Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para outros detalhes sobre este campo definido.

## <a name="patient"></a>Paciente

Estes são os campos necessários mínimos, que são um subconjunto dos campos de [perfil de pacientes Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Name.Family
2. Name.Given
3. Gênero
4. Data de nascimento
5. MRN (identificador)

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também lê os seguintes campos:

1. Name.Use
2. Name.Prefix
3. CareProvider (nesta referência do recurso de pacientes deve incluir os campos de exibição mostrados no exemplo a seguir).

* * *

    Solicitação de: GET <fhir-server>/paciente/<patient-id>
    
    Resposta: {"resourceType": "Paciente", "id": "<patient-id>".
      .
      .
      "name": [{"usar": "oficial", "prefixo": ["Mr"] "família": ["Chau"] "dado": ["Hugh"]}], "identificador": [{"usar": "oficial", "tipo": {"codificação": [{"sistema": "http://hl7.org/fhir/v2/0203", "código": "MR"}]}, "value": "1234567"}], "gênero": "masculino", "data de nascimento": "1957-06-05 ","careProvider": [{"Exibir":"Maria da Silva"}],}

* * *

Uma pesquisa de recurso usa o método POST no /Patient/_search e os seguintes parâmetros:

1. ID
2. família: contém = (procura por todos os pacientes cujo nome família contém o valor).
3. determinado =\<substring>
4. nome =\<substring>
5. Data de nascimento =(exact match)
6. \_Contagem de (número máximo de resultados que devem ser retornadas) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa, e \_contagem será usada pelo PatientsApp para limitar o número de registros retornados.
7. identificador =\<mrn>

O objetivo é conseguir pesquisa e filtro do paciente pelo seguinte:

- ID: Este é o ID de recurso que tem de cada recurso no FHIR.
- MRN: Esse é o identificador real do paciente que seria saber a equipe de início de estudos clínicos. Podemos entender que este MRN baseia-se ao tipo de identificador de recurso identificador na FHIR
- Nome
- Data de nascimento

Consulte o exemplo a seguir desta chamada.

* * *

    Solicitação: Corpo da solicitação POST <fhir-server>/paciente/_search: determinado = hugh&family = chau
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle-id>".
      .
      .
      "entry": [{"recurso": {"resourceType": "Paciente", "id": "<patient id>", "nome": [{"text": "Hugh Chau", "família": ["Chau"] "dado": ["Hugh"]}], "gênero": "masculino", "data de nascimento": "1957-06-05"}, "pesquisa": {"modo": "correspondência"}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para outros detalhes sobre este campo definido.

## <a name="observation"></a>Observação

Estes são os campos necessários mínimos, que são um subconjunto do perfil vital sinais Argonaut:

 1. Efetivo (data hora ou período)
 2. Code.Coding.Code
 3. ValueQuantity.Value

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também lê os seguintes campos:

 1. Code.Coding.Display
 2. ValueQuantity.Unit

Se usar observações do componente, a mesma lógica se aplica para Observação cada componente.

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id do paciente\>
2. classificação: desc =\<campo ex. Data\>

O objetivo é conseguir recuperar os sinais de vital mais recentes do paciente, [VitalSigns.DSTU.saz] (Observação).

* * *

    Solicitação: Obtenha <fhir-server>/Observação? paciente = <patient-id>&_sort:desc = date&category = vital-sinais
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 20, "entry": [{"recurso": {"resourceType": "Observação", "id": "<resource id>", "categoria": {"codificação": [{código":"vital sinais"}],},"código": {" codificação": [{"sistema":"http://loinc.org","código":"39156-5","exibição":"IMC"}],},"effectiveDateTime":"2009-12-01","valueQuantity": {"value": 34.4,"unidade":" kg/m2","sistema":"http://unitsofmeasure.org","código":" kg/m2"}},},.
        .
        .
      ] }

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para outros detalhes sobre este campo definido.

## <a name="condition"></a>Condição

Estes são os campos necessários mínimos, que são um subconjunto do [perfil de condição de Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code.Coding[0]. Exibição

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:

1. Data da gravação
2. Severidade

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. Count =\<results> max

Consulte o exemplo a seguir desta chamada:

* * *

    Solicitação: Obtenha <fhir-server>/condição? paciente = <patient-id>&_count = 10
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "Condição", "id": "<resource id>", "código": {"codificação": [{               "sistema": "http://snomed.info/sct", "código": "386033004", "Exibir": "Neuropathy (danos parte)"}]}, "dateRecorded": "2018-09-17", "gravidade": {"codificação": [{"syst em":"http://snomed.info/sct","código":"24484000","Exibir":"Grave"}]}},}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para outros detalhes sobre este campo definido.

## <a name="encounter"></a>Encontrar

Estes são os campos necessários mínimos, que são um subconjunto dos EUA Core encontrar perfil "deve ter" campos:

1. Status
2. Tipo [0]. Codificação [0]. Exibição

Além disso, os seguintes campos do perfil nos encontrar Core "devem suportar" fields

1. Period.Start
2. Local [0]. Location.Display

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. _sort:desc =\<campo ex. date>
3. Count =\<results> max

O objetivo é conseguir recuperar local conhecido do último do paciente. Cada ocorrência faz referência a um recurso local. A referência também deverá incluir o campo de exibição do local. Consulte o exemplo a seguir desta chamada.
* * *

    Solicitação: Obtenha <fhir-server>/ocorrência? paciente = <patient-id>&_sort:desc = date&_count = 1
    
    Resposta: {"resourceType": "Pacote", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "Encontrar", "id": "<resource id>", "identificador": [{"usar": "oficial", "value": "<id>"}], "status" : "chegou", "digite": [{"codificação": [{"Exibir": "Compromisso"}],}], "paciente": {"referência": "<patient/paciente-id>"}, "ponto": {"Iniciar": "17/09/2018 1:00:00 PM"}, "local": [{              "local": {"Exibir": "Inicial – ENT"},}]}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para outros detalhes sobre este campo definido.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos necessários mínimos, que são um subconjunto do perfil Argonaut AllergyIntolerance:

1. Code.Text
2. Code.Coding[0]. Exibição
3. Status

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também lê os seguintes campos:

1. RecordedDate
2. Note.Text
3. Reação [..]. Substance.Text
4. Reação [..]. Manifestação [..]. Texto
5. Text.Div

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. Paciente = \<id> paciente

Consulte o exemplo a seguir desta chamada:

* * *

    Solicitação: Obtenha <fhir-server>/AllergyIntolerance? paciente = <patient-id>
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "AllergyIntolerance", "id": "<resource id>", "recordedDate": "2018-09-17T07:00:00.00 0Z","substância": {"text":"Cashew nuts"},"status":"confirmado","reação": [{"substância": {"text":"cashew Porca allergenic extrair Injectable produto"},"manifestati em": [{"text":"Anaphylactic reação"}]}]}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para outros detalhes sobre este campo definido.

## <a name="medication-order"></a>Ordem de remédios

Estes são os campos necessários mínimos, que são um subconjunto do perfil Argonaut MedicationOrder:

1. DateWritten
2. Prescriber.Display
3. Medication.Display (se referência)
4. Medication.Text (se conceito)

Além dos campos Argonaut, para uma experiência de usuário excelente o aplicativo de pacientes também pode ler os seguintes campos:

1. DateEnded
2. DosageInstruction.Text
3. Text.Div

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente
2. Count =\<results> max

Consulte o exemplo a seguir desta chamada:

* * *

    Solicitação: Obtenha <fhir-server>/MedicationOrder? paciente = <patient-id>&_count = 10
    
    Resposta: {"resourceType": "Agrupam", "id": "<bundle id>", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "MedicationOrder", "id": "<resource id>", "dateWritten": "2018-09-17", "medi cationCodeableConcept": {"text":"Lisinopril 20 MG Oral Tablet"},"prescriber": {"Exibir":"Maria da Silva"},"dosageInstruction": [{"text":"1 diariamente"}]}}]}

* * *  

Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para outros detalhes sobre este campo definido.

## <a name="coverage"></a>Cobertura

Estes são os campos necessários mínimos, não cobertos por nós principais ou Argonaut perfis:

1. Outros fornecedores

Uma pesquisa de recurso usa o método GET e os seguintes parâmetros:

1. paciente =\<id> paciente

Consulte o exemplo a seguir desta chamada:

* * *

    Solicitação: Obtenha <fhir server>/cobertura? paciente = <patient-id>
    
    Resposta: {"resourceType": "Pacote", "tipo": "searchset", "total": 1, "entry": [{"recurso": {"resourceType": "Cobertura", "id": "<resource id>", "Planejar": "Não principal Insurance", "assinante": {"referência": "paciente / <patient-id> "}}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para outros detalhes sobre este campo definido.

## <a name="location"></a>Local

Este recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .

Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para outros detalhes sobre este campo definido.
