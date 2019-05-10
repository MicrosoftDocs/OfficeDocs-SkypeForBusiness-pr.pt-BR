---
title: Introdução ao Teams para Organizações de Saúde
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introdução ao Teams para Organizações de Saúde
ms.openlocfilehash: b2e7019183da06484b533fe66fd092c588c65e3f
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835437"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introdução ao Teams para Organizações de Saúde

Teams da Microsoft oferece vários recursos úteis para hospitais e outras organizações de saúde. Recursos de equipes estão em desenvolvimento para auxiliar hospitais com:

- Coordenação de atendimento médico
- Mensagens seguras
- Integração de atendimento médico Record (EHR) eletrônicos
- Integração de trabalhador de Firstline

## <a name="care-coordination---microsoft-teams-patients-app"></a>Equipes de atendimento médico coordenação - Microsoft app os pacientes

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams agora possui uma solução de coordenação de atendimento médico específica para as organizações de saúde para ajudá-los a atender às sua objetivo final de fornecer o melhor aos pacientes. O x da solução de coordenação de atendimento médico, o aplicativo de pacientes de equipes da Microsoft, é um aplicativo de guia de terceiros primeiro que integra com sistemas de (EHR) registros saúde eletrônicos usando uma interface de recursos de interoperabilidade de atendimento médico Fast ([FHIR](https://www.hl7.org/fhir/)) para trazer valiosos informações médicas em Teams da Microsoft.  

A solução de coordenação de atendimento médico pode estabelecer interface com fornecedores de Software independentes (ISVs) que o aplicativo de pacientes podem se conectar aos seus sistemas EHR usando existente padrões de dados de integridade, como HL7v2 e FHIR. Parceiros do Microsoft com as seguintes líderes do setor para estabelecer a integração de registros de saúde eletrônicos com equipes:

- Datica (por meio da oferta seus [CMI](https://datica.com/compliant-managed-integration/) )
- Informações Cloverleaf (pela [Ponte de FHIR informações](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (por meio do [R ^ server FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (por meio de [Corolar em FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Uma integração EHR e interoperabilidade parceiro tentando implementar Teams da Microsoft para uma organização de assistência médica precisa fornecer o aplicativo de pacientes uma conexão segura e autenticada com sistemas EHR da organização de assistência médica. Isso permite que o fluxo de (somente leitura) one-direcional dos pacientes registros relevantes no aplicativo os pacientes. O aplicativo de pacientes entende o formato FHIR, portanto, o parceiro também é responsável por transformar os dados agregados de vários outros formatos como HL7v2, etc. em FHIR DSTU2 ou STU3.

<br>

![Integração do EHR](../../media/ehr-1.png)

<br>

O aplicativo de pacientes se integra com sistemas de registros (EHR) de saúde eletrônicos e permite que se preocupar provedores para se comunicar sobre do paciente em tempo real dentro da plataforma segura das equipes. O aplicativo de pacientes é o primeiro grande investimento na área de coordenação de atendimento médico que pretende resolver os seguintes desafios:

- Baixa eficiência em transferências e comunicação crítica por meio de experiência do paciente
- Silos informações que cria a carga administrativa
- Insatisfação entre os clínicos com ferramentas de colaboração complexa e fragmentado
- Coordenação de atendimento médico de pessoal ineficientes que pode gravar a hora de início de estudos clínicos muito cara

Microsoft Teams permite que os médicos, os médicos, enfermeiros e outros funcionários colaborar com eficiência por:

- Sendo parte de uma única equipe virtualizada que funciona e colabora em documentos do Office
- Ter conversas persistentes sobre pacientes diferentes que precisam de atenção
- Usando canais com guias como uma maneira de estruturar seu trabalho, com a ajuda adicional de guias aos quais eles podem fixar fontes de informações
- Usando reuniões de canal com o poder do áudio de equipes, vídeo, compartilhamento de tela, gravação e recursos de transcrição para gerenciar reuniões diárias
- Usando o aplicativo de pacientes para curate uma lista de alto risco pacientes que devem ser monitoradas e extrai seus detalhes mais recentes do sistema EHR. O aplicativo de pacientes próprio adiciona os seguintes recursos para Teams da Microsoft:

    - Capacidade de criar vários paciente lista dentro de um único canal.
    - Capacidade de visualizar e classificar as informações exibidas sobre os pacientes através de colunas configuráveis.
    - Capacidade de autoprovisionar o aplicativo por meio de um modelo de equipe.
    - Disponível em aplicativo equipes para iOS e Android para profissionais de saúde móveis primeiro, bem como o cliente de desktop e web Teams da Microsoft.
    - Suporte para as versões de FHIR DSTU2 e STU3 por meio de análise de declaração de conformidade.
    - Logs de auditoria para todas as ações de exibir e pesquisar em sua interface de usuário para a proteção pi por diretrizes HIPAA.

O aplicativo de pacientes é criado na plataforma de extensibilidade de equipes e aproveita a estrutura de guias para exibir conteúdo de pacientes rico dentro de um canal. Para saber mais sobre a própria plataforma e de outros aplicativos de equipes, consulte [Apps para equipes da Microsoft](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> O aplicativo de pacientes está no modo de visualização particular e a interface FHIR está em beta. Versões lançadas não deverão ser compatíveis com versões anteriores.

![Captura de tela de app os pacientes](../../media/ehr-2.png)

Consulte [Integrando registros de saúde eletrônicos em equipes da Microsoft](patients-app.md) para obter detalhes de implementação.

## <a name="templates"></a>Modelos

Novos modelos para a criação de equipes foram desenvolvidos para aplicar a hospitalares e mais esperados em breve. Isso facilita criar equipes usado por profissionais de saúde para coordenar o atendimento médico para pacientes em vários departamentos ou alas. Consulte o [guia de Introdução com modelos de equipes para organizações de saúde](healthcare-templates.md). As equipes podem ser iniciadas para departamentos internos, como cardiologia, ou para alas de atendimento médico, e mais modelos estão em desenvolvimento.

## <a name="secure-messaging"></a>Mensagens seguras

Colaboração de suporte a mensagens em equipes de atendimento médico, incluindo vários novos recursos de segurança:

- O remetente da mensagem pode definir uma prioridade especial para a sua mensagem, para que o destinatário será notificado repetidamente até que eles devem ler a mensagem.
- O remetente da mensagem pode solicitar uma confirmação de leitura, para que sejam notificados quando uma mensagem enviados por eles foi lido pelo remetente da mensagem.
- 

Juntos, esses recursos permitem atenção mais rápida às mensagens urgentes e confiança que a mensagem foi recebida e ler. Novo equipes de atendimento médico usando esses recursos podem ser criadas em uma base por pacientes. Esses recursos são baseadas na diretiva e podem ser atribuídos aos indivíduos ou equipes inteiros.

Para obter mais detalhes, consulte [Introdução ao Secure Messaging políticas para as organizações de saúde](messaging-policies-hc.md) .

Também para mensagens seguras está relacionado a capacidade de ter outros inquilinos federados por organizações de saúde, permitindo a comunicação entre locatários mais rica. (consulte [Manage external access (federação) em equipes da Microsoft](../../manage-external-access.md)).

## <a name="firstline-worker-integration"></a>Integração de trabalhador de Firstline

Microsoft Teams se integra ao trabalhador Firstline, que pode ser usado para coordenar shift recursos de pessoal e mais.

 Consulte os seguintes artigos:

- [Mover suas equipes da Microsoft StaffHub para mudanças na Teams da Microsoft](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [Gerencie o aplicativo Turnos para sua organização no Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
