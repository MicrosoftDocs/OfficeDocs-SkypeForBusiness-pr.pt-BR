---
title: Interface do DSTU2 de integração do EHR e aplicativo pacientes
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
description: Saiba mais sobre a especificação de interface DSTU2 no Teams, incluindo configurar ou reconfigurar um servidor FHIR para trabalhar com o aplicativo Microsoft Teams pacientes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ab502f66785af7947185fb0fbee0d3a55dd70c67
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367601"
---
# <a name="dstu2-interface-specification"></a>Especificação de interface DSTU2

> [!IMPORTANT]
> **A partir de 30 de outubro de 2020, o aplicativo pacientes será preterido, e os usuários não poderão mais instalá-lo na App Store da equipe. Recomendamos que você comece a usar o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Microsoft Teams hoje mesmo.**
>
>Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe. Quando o aplicativo pacientes é desativado, todos os dados associados a ele serão mantidos nesse grupo, mas não poderão mais ser acessados por meio da interface do usuário. Os usuários atuais podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>O [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. Com listas, o cuidado com equipes pode criar listas de pacientes usando o modelo de pacientes incorporado, do zero ou importando dados para o Excel. Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A configuração ou a reconfiguração de um servidor FHIR para trabalhar com o aplicativo pacientes do Microsoft Teams requer noções básicas sobre quais dados o aplicativo precisa acessar. O servidor FHIR deve dar suporte a solicitações POST usando pacotes para os seguintes recursos:

- [Aguarde](#patient)
- [Observações](#observation)
- [Condição](#condition)
- [Encontrá](#encounter)
- [Allergy intolerância](#allergyintolerance)
- [Análise](#coverage)
- [Pedido de medicação](#medication-order)
- [Local](#location)

> [!NOTE]
> O recurso de paciente é o único recurso obrigatório (sem que o aplicativo não seja carregado. No entanto, é recomendável que o parceiro implemente o suporte para todos os recursos mencionados acima, por especificações fornecidos abaixo, para obter a melhor experiência do usuário final com o aplicativo pacientes do Microsoft Teams.

Consultas do aplicativo Microsoft Teams pacientes para mais de um recurso poste um pacote (lote) de solicitações para a URL do servidor FHIR. O servidor processa cada solicitação e retorna um pacote dos recursos correspondentes a cada solicitação. Para obter mais informações e exemplos, consulte [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Todos os recursos de FHIR a seguir devem ser acessíveis pela referência a recursos diretos.

## <a name="conformance-minimum-required-field-set"></a>Conjunto de campos obrigatórios mínimos de conformidade

 O servidor FHIR deve implementar a instrução de conformidade para que possamos ter um resumo factual de seus recursos. Esperamos os parâmetros a seguir em um servidor FHIR DSTU2:

1. DEIXAR
   1. Modo
   2. Haja
   3. Recurso: tipo
   4. Segurança: [extensão para URIs OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (nosso código requer que isso compreenda para qual versão devemos pivotá-lo como suporte a várias versões.)

Consulte [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="patient"></a>Aguarde

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos de [perfil do paciente do Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Nome. família
2. Nome. fornecido
3. Sexo
4. DataDeNascimento
5. MRN (identificador)

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:

1. Name. Use
2. Name. Prefix
3. Cuidado: (essa referência ao recurso do paciente deve incluir os campos de exibição mostrados no exemplo a seguir.)

* * *

    Solicitação: Obtenha o <fhir>/patient/<o ID do paciente>
    
    Resposta: {"resourceType": "paciente", "ID": "<paciente-ID>",.
      .
      .
      "nome": [{"Use": "Official", "prefix": ["Sr"], "família": ["Chau"], "atribuído": ["Hugh"]}], "identificador": [{"usar": "oficial", "digite": {"codificação": [{"System": " https://hl7.org/fhir/v2/0203 ", "código": "Mr"}]}, "valor": "1234567", "cuidadosprovider": "macho", "datadenascimentoe": "1957-06-05", "cuidadosprovider": [{"display": "Jane Doe"}],}

* * *

Uma pesquisa de recursos usa o método postar em/patient/_search e os seguintes parâmetros:

1. %
2. Family: Contains = (procura por todos os pacientes cujo nome de família contenha o valor.)
3. especificado =\<substring>
4. nome =\<substring>
5. DataDeNascimento = (correspondência exata)
6. \_contagem (número máximo de resultados que devem ser retornados) <br> A resposta deve conter a contagem total de registros retornados como resultado da pesquisa e a \_ contagem será usada pelo PatientsApp para limitar o número de registros retornados.
7. identificador =\<mrn>

O objetivo é poder pesquisar e filtrar por um paciente da seguinte maneira:

- ID: essa é a ID do recurso que cada recurso no FHIR tem.
- MRN: esse é o identificador real do paciente que a equipe clínica saberia. Compreendemos que esse MRN é baseado no tipo de identificador dentro do recurso identificador do FHIR
- Nome
- DataDeNascimento

Consulte o exemplo a seguir desta chamada.

* * *

    Solicitação: POST <fhir-Server>/patient/_search corpo da solicitação: especificado = Hugh&Family = Chau
    
    Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>",.
      .
      .
      "entrada": [{"recurso": {"resourceType": "paciente", "ID": "<paciente-ID>", "nome": [{"texto": "Hugh Chau", "família": ["Chau"], "determinado": ["Hugh"]}], "gênero": "macho", "Datadenascimentoe": "1957-06-05"}, "localizar": {"Mode": "matching"}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="observation"></a>Observações

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil de sinais Argonaut vital:

 1. Efetivo (data e hora ou ponto)
 2. Code. Coding. Code
 3. Valor de ValueQuantity. valor

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:

 1. Code. Coding. display
 2. ValueQuantity. unidade

Se estiver usando observações de componente, a mesma lógica se aplica a cada observação de componente.

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<patient id\>
2. classificar: desc =\<field ex. date\>

O objetivo é poder recuperar os mais recentes sinais essenciais para um paciente, [VitalSigns. DSTU. Saz] (observação?).

* * *

    Solicitação: Obtenha o <fhir-Server>/Observation? paciente =<o ID do paciente>&_sort:d ESC = data&Category = sinais essenciais
    
    Resposta: {"resourceType": "pacote", "ID": "<pacote-ID>", "digite": "searchset", "total": 20, "entry": [{"Resource": {"resourceType": "reobservação", "ID": "<Resource-ID>", "categoria": {"codificação": "código": "informativo-sinais"}],}, "código": {"codificação": [{"System": " http://loinc.org ", "código": "39156-5", "display": "BMI"}],}, "effectiveDateTime": "2009-12-01", "valueQuantity": {"valor": 34,4, "unidade": "kg/m2", "sistema": " http://unitsofmeasure.org ", "código": "kg/m2"}},},.
        .
        .
      ] }

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="condition"></a>Condição

Estes são os campos mínimos obrigatórios, que são um subconjunto do [perfil da condição Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. Mostrar

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

1. Data de gravação
2. Gravidade

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<patient id>
2. _count =\<max results>

Consulte o seguinte exemplo desta chamada:

* * *

    Solicitação: Obtenha o <fhir-Server>/Condition? paciente =<paciente-ID>&_count = 10
    
    Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": "ID": "<Resource-ID": {"resourceType": "Condition", "ID": "Resource-ID>", "código": {"codificação": [{"sistema": " http://snomed.info/sct ", "código": "386033004", "vídeo": "2018-09-17", ","}]}, "dateRecorded": "", "Severity": {"Coding": [{"System": " http://snomed.info/sct ", "código": "24484000", "display": "severado}]}},}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="encounter"></a>Encontrá

Estes são os campos mínimos obrigatórios, que são um subconjunto dos campos perfil do núcleo dos EUA "deve ter":

1. Situação
2. Digite [0]. Codificação [0]. Mostrar

Além disso, os seguintes campos dos EUA enfrentam os campos "deve dar suporte" do perfil principal

1. Período. início
2. Local [0]. Location. display

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<patient id>
2. _sort: desc =\<field ex. date>
3. _count =\<max results>

O objetivo é poder recuperar o último local conhecido do paciente. Cada encontro faz referência a um recurso de localização. A referência também incluirá o campo de exibição do local. Consulte o exemplo a seguir desta chamada.
* * *

    Solicitação: Obtenha o <fhir-Server>/Encounter? paciente =<o ID do paciente>&_sort:d ESC = data&_count = 1
    
    Resposta: {"resourceType": "Bundle", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "encontrar", "ID": "<Resource-ID>", "identificador": [{"usar": "oficial", "valor": " <id> "}], "status": "chegado", "tipo": [{"codificação": [{"exibir": "compromisso"}],}], "paciente": {"referência": "paciente/<paciente-id>"}, "período": {"Iniciar": "09/17/2018 1:00:00 PM"}, "local": [{"Location": {"display": "Clinic-ENT"},}]}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) para obter outros detalhes sobre esse conjunto de campos.

## <a name="allergyintolerance"></a>AllergyIntolerance

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut AllergyIntolerance:

1. Code. Text
2. Code. Coding [0]. Mostrar
3. Situação

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também lê os seguintes campos:

1. RecordedDate
2. Observação. texto
3. Reação [..]. Substância. Text
4. Reação [..]. Manifestação [..]. Textos
5. Text. div

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. Paciente =  \<patient id>

Consulte o seguinte exemplo desta chamada:

* * *

    Solicitação: Obtenha o <fhir-Server>/AllergyIntolerance? paciente =<o ID do paciente>
    
    Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": "ID": "<Resource-ID": {"resourceType": "AllergyIntolerance", "ID": "Resource-ID>", "recordedDate": "2018-09-17T07:00:00.000 Z", "substância": {"texto": "Cashew porcas"}, "status": "confirmado", "reação": [{"substância": {"texto": "Cashew porca allergenic extrair produto injetado"}, "manifestoing": [{"texto": "anaphylactic reação"}]}]}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="medication-order"></a>Pedido de medicação

Estes são os campos mínimos obrigatórios, que são um subconjunto do perfil Argonaut MedicationOrder:

1. DateWritten
2. Preparador. exibição
3. Medicação. display (se referência)
4. Medicação. Text (se conceito)

Além dos campos Argonaut, para uma excelente experiência do usuário, o aplicativo pacientes também pode ler os campos a seguir:

1. DateEnded
2. DosageInstruction. Text
3. Text. div

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<patient id>
2. _count =\<max results>

Consulte o seguinte exemplo desta chamada:

* * *

    Solicitação: Obtenha o <fhir-Server>/MedicationOrder? paciente =<paciente-ID>&_count = 10
    
    Resposta: {"resourceType": "Bundle", "ID": "<pacote-ID>", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"texto": "Janete-Tablet MG"}, "preparador": {"exibir": "Janete"}, "dosageInstruction": [{"texto": "1 diário"}]}}]}

* * *  

Consulte [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="coverage"></a>Análise

Estes são os campos mínimos obrigatórios, não cobertos pelos perfis centrais dos EUA ou Argonaut:

1. Payor

Uma pesquisa de recursos usa o método GET e os seguintes parâmetros:

1. paciente =\<patient id>

Consulte o seguinte exemplo desta chamada:

* * *

    Solicitação: Obtenha o <fhir-Server>/Coverage? paciente =<o ID do paciente>
    
    Resposta: {"resourceType": "pacote", "tipo": "searchset", "total": 1, "entry": [{"Resource": {"resourceType": "Coverage", "ID": "<Resource-ID>", "plano": "não há seguro principal", "assinante": {"referência": "paciente/<paciente-identificação>"}}}]}

* * *

Consulte [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) para obter outros detalhes sobre esse conjunto de campos.

## <a name="location"></a>Local

Esse recurso está sendo usado apenas como uma referência no recurso [encontrar](#encounter) .

Consulte [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) para obter outros detalhes sobre esse conjunto de campos.
