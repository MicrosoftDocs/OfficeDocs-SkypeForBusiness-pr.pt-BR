---
title: Introdução ao Teams para Organizações de Saúde
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
ms.reviewer: ''
description: Saiba mais sobre os recursos de assistência médica que incluem coordenação, Secure Messaging, telehealth, integração do EHR e primeira integração do sistema de trabalho.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d2a77e5e7e696e20efb13a5c805968fc3af3204
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138101"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Introdução ao Teams para Organizações de Saúde

O Microsoft Teams oferece diversos recursos úteis para hospitais e outras organizações de assistência médica. Os recursos do teams estão em desenvolvimento para ajudar hospitais com:

- Coordenação e colaboração de cuidados
- Mensagens seguras
- Telehealth
- Integração do EHR (Electronic Healthcare Record) 
- Integração do sistema de trabalho de primeira mão 

O conteúdo desta seção baseia-se nos recursos básicos do Teams, como reuniões, chamadas e mensagens e pressupõe que você já implantou o Microsoft Teams em sua organização. Se você ainda não distribuiu o Microsoft Teams, comece lendo [como implantar o Microsoft Teams](../../How-to-roll-out-teams.md).

## <a name="care-coordination---microsoft-teams-patients-app"></a>Coordenação de cuidado-aplicativo pacientes do Microsoft Teams

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Agora o Microsoft Teams tem uma solução de coordenação de cuidado específica para organizações de assistência médica para ajudar a oferecer o melhor atendimento ao paciente. O crux da solução de coordenação de cuidados, o aplicativo Microsoft Teams pacientes, é um aplicativo de guia de primeira parte que se integra aos sistemas EHR (Electronic Health Record) que usam uma interface de recursos de interoperabilidade do Fast Healthcare ([FHIR](https://www.hl7.org/fhir/)) para trazer informações médicas importantes para o Microsoft Teams em contexto para habilitar a colaboração clínica e a comunicação.  

A solução de coordenação de cuidados pode ser uma interface com fornecedores de software independentes (ISVs) que podem conectar o aplicativo pacientes a seus sistemas EHR usando padrões de dados de integridade existentes, como HL7v2 e FHIR. A Microsoft faz parcerias com os seguintes líderes do setor para estabelecer a integração de registros eletrônicos de integridade com o Microsoft Teams:

- Datica (por meio da oferta [CMI](https://datica.com/compliant-managed-integration/) )
- Infor Cloverleaf (por meio da [ponte infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (por meio do [servidor R ^ FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (por meio [de Corolar em FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Uma integração do EHR e parceiro de interoperabilidade que tentam implementar o Microsoft Teams para uma organização de provedor de assistência médica precisam fornecer ao aplicativo pacientes uma conexão segura e autenticada com os sistemas EHR da organização do provedor de assistência médica. Isso permite que o fluxo unidirecional (somente leitura) dos registros do paciente pertinentes para o aplicativo pacientes. O aplicativo pacientes compreende o formato FHIR, portanto, o parceiro também é responsável por transformar os dados agregados de vários outros formatos, como HL7v2, etc., em FHIR DSTU2 ou STU3.

<br>

![Ilustração realçando a coordenação e a colaboração](../../media/ehr-1.png)

<br>

O aplicativo pacientes se integra a sistemas EHR (Electronic Health Records) e permite que provedores de cuidado se comuniquem sobre o atendimento ao paciente em tempo real na plataforma segura da equipe. O aplicativo pacientes é o primeiro grande investimento na área de coordenação da área de atendimento, cujo objetivo é atender aos seguintes desafios:

- Baixa eficiência em mão-baixa e comunicação crítica por meio da experiência do paciente
- Informações em silos que criam sobrecargas administrativas
- Dessatisfação entre clínicos com ferramentas de colaboração complexas e fragmentadas
- Coordenação ineficiente de assistência interna que pode gravar um período clínico muito caro

O Microsoft Teams permite que médicos, clínicos, retenhas e outros funcionários colaborem com eficiência:

- Fazer parte de uma única equipe virtualizada que funciona e colabora em documentos do Office
- Ter conversas persistentes sobre diferentes pacientes que precisam de atenção
- Usando canais com guias como uma maneira de estruturar seu trabalho, com ajuda adicional das guias às quais elas podem fixar fontes de informações
- Usar reuniões de canal com o poder de recursos de áudio, vídeo, compartilhamento de tela, gravação e transcrição do teams para gerenciar reuniões diárias
- Usar o aplicativo pacientes para auxiliar uma lista de pacientes de alto risco que devem ser monitorados e obtém seus detalhes mais recentes do sistema EHR. O próprio aplicativo pacientes adiciona os seguintes recursos ao Microsoft Teams:

    - Capacidade de criar várias listas de pacientes em um único canal.
    - Capacidade de exibir e classificar informações exibidas sobre pacientes por meio de colunas configuráveis.
    - Capacidade de configurar automaticamente o aplicativo por meio de um modelo de equipe.
    - Disponível no aplicativo Teams para iOS e Android para dispositivos móveis da primeira assistência médica, bem como cliente da Web do Microsoft Teams e da área de trabalho.
    - Suporte para versões do FHIR DSTU2 e do STU3 por meio da análise da declaração de conformidade.
    - Logs de auditoria para todas as ações de exibição e pesquisa em sua interface de usuário para proteger as diretrizes de PHI para HIPAA.

O aplicativo pacientes é criado na plataforma de extensibilidade do Teams e aproveita a estrutura guias para exibir conteúdo rico do paciente em um canal. Para saber mais sobre outros aplicativos do Teams e a plataforma em si, consulte [aplicativos para o Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> O aplicativo pacientes está em visualização particular e a interface FHIR está em beta. Versões lançadas não devem ser compatíveis com versões anteriores.

![Captura de tela do aplicativo pacientes em dispositivos móveis e desktop](../../media/ehr-2.png)

Consulte [integrando os registros eletrônicos de assistência médica ao Microsoft Teams](patients-app.md) para obter detalhes de implementação.

## <a name="teams-templates"></a>Modelos de equipe

Novos modelos para a criação de equipes foram desenvolvidos para serem aplicados a uma configuração do hospital e mais esperadas em breve. Isso facilita a criação de equipes que os funcionários da área de saúde usam para coordenar o cuidado com pacientes em vários departamentos ou em diante. Consulte [introdução aos modelos de equipe para organizações de assistência médica](healthcare-templates.md). As equipes podem ser iniciadas para departamentos internos, como cardiologia ou para portabilidade, e mais modelos estão em desenvolvimento.

## <a name="lists-app"></a>Aplicativo listas

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

O aplicativo listas no Teams ajuda as equipes a acompanhar informações e organizar o trabalho. O aplicativo é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. As listas podem ser criadas do zero, de modelos predefinidos ou importando dados para o Excel.

As equipes de cuidado podem usar o modelo pacientes para começar. Elas podem criar listas para acompanhar as necessidades e o status dos pacientes. Os dados existentes do paciente em planilhas do Excel podem ser trazidos para criar uma lista no Teams. Essas listas podem ser usadas para cenários como rodadas e monitoramento de pacientes para coordenar o cuidado.

Por exemplo, um enfermeira de cobrança cria uma lista de pacientes em uma equipe que inclui todos os membros da equipe. Durante os XX, a equipe de atendimento ao cliente em seus dispositivos móveis e atualizar as informações dos pacientes na lista, que todos os membros da equipe podem ver para permanecer em sincronização. Em sessões de arredondamento em que a equipe de atendimento se reúne para discutir e avaliar as principais métricas de desempenho da saúde para garantir que um paciente esteja no caminho de ponto de partida correto para a descarga, ele pode compartilhar essas informações usando o Microsoft Teams em uma tela grande de exibição. Cuidado os membros da equipe que não estão no local podem ingressar remotamente.

Aqui está um exemplo de lista que foi configurada para o arredondamento de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de tela da lista de exemplos para o arredondamento de pacientes":::

Para saber mais, consulte [gerenciar o aplicativo listas para sua organização no Teams](../../manage-lists-app.md).

## <a name="secure-messaging"></a>Mensagens seguras

As mensagens seguras dão suporte à colaboração em equipes de cuidado, incluindo vários novos recursos:

- Um remetente de mensagem pode definir uma prioridade especial para a mensagem, para que o destinatário seja repetidamente notificado até que ele leia a mensagem.
- Um remetente de mensagem pode solicitar uma confirmação de leitura para que elas sejam notificadas quando uma mensagem enviada por ele for lida pelo destinatário da mensagem.


Juntos, esses recursos permitem uma atenção mais rápida para mensagens urgentes e confiança de que a mensagem foi recebida e lida. As novas equipes de cuidado ao usar esses recursos podem ser criadas em uma base por paciente. Esses recursos são baseados em políticas e podem ser atribuídos a indivíduos ou a equipes inteiras.

Consulte [introdução ao Secure Messaging Policies for Healthcare para empresas](messaging-policies-hc.md) para obter mais detalhes.

Também relacionados a mensagens seguras é a capacidade de ter outros locatários agrupados por organizações de assistência médica, permitindo comunicações mais ricas entre os locatários. (Consulte [gerenciar o acesso externo (Federação) no Microsoft Teams](../../manage-external-access.md)).

## <a name="firstline-worker-integration"></a>Integração do trabalho do primeiro lugar

O Microsoft Teams integra-se com o primeiro trabalhador, que pode ser usado para coordenar os recursos de pessoal de mudança e muito mais. Consulte [gerenciar o aplicativo turnos para sua organização no Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).
