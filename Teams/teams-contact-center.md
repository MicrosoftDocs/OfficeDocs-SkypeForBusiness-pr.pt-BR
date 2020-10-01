---
title: Central de contatos do teams
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: Uma visão geral da solução integrada do centro de contatos como serviço (CCaaS) para o Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: ccd4456b006d8b27fd0aa2ec88d6467fe86fea8b
ms.sourcegitcommit: c49698e03fa3bdd7c82496189b200ac6bb4e05a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322280"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Integrações do centro de contato do Microsoft Teams

A integração de soluções populares de centro de contato com o Microsoft Teams é uma necessidade comum para os clientes implantarem recursos de chamada de equipe.  Este artigo fornece uma visão geral de como as soluções do centro de contato podem ser integradas ao Microsoft Teams e informações adicionais sobre as soluções de parceiros que participam do programa de certificação da central de contatos do Microsoft Teams conectado.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>O que é a integração da central de contatos do Microsoft Teams?

As centrais de contatos de hoje fornecem muito mais do que o suporte – elas atuam como um dos principais veículos de interação e comentários não filtrados sobre a experiência de um cliente com uma marca. Devido à amplitude de canais que os clientes de hoje preferirão se envolver – telefone, e-mail, texto, social e o volume expandido de pontos de contato associados a processos de compra de presente dia, muitas organizações perceberam duas realidades adicionais:

1. Cada membro da organização tem o potencial de estar envolvido na envolvimento de um cliente diretamente e, portanto, precisa estar equipado com as ferramentas apropriadas.

2. Esse escopo expandido de interações com o cliente exige ferramentas que podem ajudar a aumentar a consistência, a melhoria constante e a escala.

O Microsoft Teams é compatível com os fluxos de trabalho de interação do cliente atuando como o Hub para conexão interna e externa do cliente em todos os modos de comunicação, incluindo chat, reuniões com vídeo e chamadas. Para algumas empresas, os recursos de [voz em nuvem](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)do Microsoft Teams, incluindo [atendedor automático](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) e [filas de chamadas](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), fornecem os recursos e a configuração para atender às suas necessidades.

Para outras pessoas que desejam soluções integradas com ferramentas comerciais e fluxos de trabalho para impulsionar a jornada do cliente, o Microsoft Teams também integra-se a alguns dos provedores de soluções do serviço e do CCaaS (centro de contatos) líderes do setor.

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centro de contato conectado para o programa de certificação do Microsoft Teams

As APIs que permitem que os parceiros desenvolvam e integrem o CCaaS Solutions for Teams estão disponíveis com a licença avançada de comunicação. Além disso, desenvolvemos o programa de certificação da central de contatos conectado para Microsoft Teams para fornecer aos clientes a garantia de que cada solução de parceiro participante foi testada e verificada para fornecer a qualidade, a compatibilidade e a confiabilidade esperadas das soluções da Microsoft.

Os parceiros a seguir estão no processo de certificação da solução para o Microsoft Teams e estão prontos para contratar clientes:

| **Sócio**                                                                                                                              | **Site da solução**                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Anywhere365 | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| Competella | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| ComputerTalk | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| ContactCenter4All | https://docs.microsoft.com/microsoftteams/teams-contact-center#connected-contact-center-for-microsoft-teams-certification-program |
| Enghouse Interactive | http://www.enghouseteams.com/                                                       |
| Five9 | https://www.five9.com/products/application-integration/uc-integration                                                   |
| Genesys | https://www.genesys.com/microsoft                                                                                   |
| Tecnologias Landis | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| Luware | https://luware.com/en/solutions/                                                                                       |
| BOM contato | https://www.niceincontact.com/microsoft-teams                                                            |
| Tendfor | https://www.tendfor.com/en/                                                                                     |

Esta lista será atualizada à medida que mais parceiros entrarem e atenderem aos critérios de certificação.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Como as soluções do centro de contato funcionam no Microsoft Teams?

O Microsoft Teams oferece uma gama de recursos para dar suporte ao desenvolvimento de soluções de voz de terceiros, incluindo:

1. [Conectividade de roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [APIs de comunicação na nuvem do Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plataforma e extensibilidade do teams

4. SDKs do Microsoft Teams

Juntos, esses recursos permitem três modelos de integração:

  - **Conectar** (via roteamento direto)

  - **Conectar e estender** (direcionamento direto, APIs de gráfico e plataforma de aplicativos do Teams)

  - **Estender e poder** (inserir SDKs do teams em aplicativos do 3P para interações de equipes nativas)

### <a name="connect"></a>Conectado

Esse modelo conecta CCaaS parceiros à infra-estrutura do sistema telefônico do Microsoft Teams, permitindo o roteamento, configuração e informações do sistema aprimoradas. Nesse modelo, a solução de parceiro da central de contatos também pode fornecer serviços de telefonia para números e usuários selecionados.

Os agentes que usam soluções criadas no modelo de conexão podem coletar informações & insights e, se necessário, transferir chamadas para especialistas no assunto diretamente, aproveitando a presença do SME no Teams para garantir sua disponibilidade.

As organizações podem ter certeza de que as chamadas são direcionadas para o agente ideal Configurando o assistente virtual automatizado e filas de roteamento baseado em habilidades.

**Destaques do recurso:**

Embora a seguinte não seja uma lista abrangente de recursos de recursos para esse modelo de integração, as áreas de foco incluem:

  - Office 365 Authn para agentes para permitir que os agentes se conectem ao locatários da Microsoft a partir de seu cliente CCaaS integrado 

  - Indicação de presença de usuários do teams 

  - Fluxos de chamadas via roteamento direto (conforme indicado em planos de teste) 

  - Suporte a transferências e chamadas em grupo com usuários do teams 

  - APIs do teams Graph e APIs de comunicação na nuvem para integração com o Microsoft Teams 

  - Capaz de dar suporte ao entroncamento SIP multilocatário para dar suporte a vários clientes no SBC do parceiro.  

  - Parceiros para implementar [ <span class="underline">o Microsoft Certified Session Border Controller (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Conectar e estender

Esse modelo estende as experiências do Team Center e do agente por meio da integração com o cliente do teams usando a [plataforma de cliente do teams](https://docs.microsoft.com/microsoftteams/platform/overview), [APIs do teams Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e a [API de comunicação em nuvem no Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) e usa o sistema de telefone de equipe para todas as chamadas e experiências de controle de chamada Nesse modelo, o parceiro da central de contatos atua como uma operadora de telefonia junto com o Microsoft 365.

Aproveitando as soluções de conexão e de extensão, os agentes podem se beneficiar de notas contextuais dinâmicas que correlacionam dados de vários sistemas antes de iniciar um envolvimento e, em seguida, evitar a troca de contexto dispendiosa ao trabalhar de forma nativa dentro do teams para colaboração interna e comunicações externas.

As organizações podem projetar fluxos de trabalho e configurações de roteamento avançadas para o indivíduo e medir a qualidade do sistema e das interações.

**Destaques do recurso:**

Embora a seguinte não seja uma lista abrangente de recursos de recursos para esse modelo de integração, ele destaca as principais áreas de foco:

  - APIs do teams Graph e APIs de comunicação na nuvem para integração com o Microsoft Teams 

  - Aplicativo baseado em equipes para experiências de agente 

  - Teams como o ponto de extremidade de chamada primária para os agentes 

  - Chamadas do cliente do teams para todos os controles de chamada

  - Aplicativo de experiência do agente também deve poder funcionar no Microsoft Teams Web e no cliente móvel

  - Análises, gerenciamento de fluxo de trabalho, experiências baseadas em função para agentes no aplicativo CCaaS no Teams

  - Experiências de chat e colaboração integradas a clientes do Microsoft Teams 

  - Preserve o desempenho e a qualidade das experiências do cliente das equipes em todos os aplicativos  

### <a name="extend-and-power"></a>Estender e desligar

Este modelo permite que os parceiros criem aplicativos de voz baseados no Azure nativos, aproveitando a infraestrutura de chamadas e a plataforma do cliente para oferecer soluções modernas e inteligentes para a conexão colaborativa de cliente e agente. A meta de estender e poder é Stoker a criatividade do desenvolvedor e impulsionar a produtividade do cliente.

Criando diretamente no Azure, os parceiros podem implantar e provisionar rapidamente a solução em todas as regiões e regiões da equipe, benefitting da nossa rede de comunicação global compartilhada, aproveitando, ao mesmo tempo, os benefícios do armazenamento, da computação e da análise do Azure & serviços cognitivas.

Com o modelo de integração de extensão e energia, os parceiros podem fornecer agentes de centro de contato com experiências de comunicação de Omni-Channels e, ao mesmo tempo, incorporar inteligência artificial para personalizar como e quando os participantes ou outros serviços estão envolvidos em uma chamada, aproveitando a [API de comunicação em nuvem no Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).

**Destaques do recurso:**

Embora a seguinte não seja uma lista abrangente de recursos de recursos para esse modelo de integração, essas áreas de destaque, além das fornecidas pelo modelo Connect e Extend.

  - Experiências de agente formal habilitadas nativamente para comunicação de canal de Omni via SDK do teams 

  - Aproveitar os serviços de colaboração de equipe para colaboração do agente e interações com o cliente  

  - Provisionamento rápido de serviços de nuvem, implantação em qualquer lugar 

  - Controle de conversa direto e interação com usuários durante conversas de equipes 

### <a name="comparing-connected-contact-center-integration-models"></a>Comparando modelos de integração à central de contatos conectados

Revise a tabela abaixo para obter uma visão geral dos modelos de integração aos quais o Microsoft Teams dá suporte.

<table>
<thead>
<tr class="header">
<th></th>
<th><strong>Aplicativos de voz do teams</strong></th>
<th><strong>Conectado</strong></th>
<th><strong>Connect + extend</strong></th>
<th><strong>Estender + potência</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modelo de serviço na nuvem</td>
<td>Azure</td>
<td>Sócio</td>
<td><p>Parceiro +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>Quem opera a solução?</td>
<td>Microsoft</td>
<td>Sócio</td>
<td>Sócio</td>
<td>Sócio</td>
</tr>
<tr class="odd">
<td>Entrada do M365</td>
<td>Sim</td>
<td>Sim</td>
<td>Sim</td>
<td>Sim</td>
</tr>
<tr class="even">
<td>Usuários com chamadas com o Microsoft Teams?</td>
<td>Informal, SME</td>
<td>Informal, SME</td>
<td>Informal, SME, formal</td>
<td>Informal, SME, formal</td>
</tr>
<tr class="odd">
<td>A experiência de IW/SME</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>Extensions</p></td>
<td><p>Teams +</p>
<p>Extensions</p></td>
</tr>
<tr class="even">
<td>Conectividade do serviço</td>
<td>Plataforma<br />
(Planos de chamada + DR)</td>
<td>Roteamento direto</td>
<td>Roteamento direto</td>
<td>Plataforma<br />
(Planos de chamada + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Próximas etapas

Se você for um fornecedor que está procurando participar do programa de certificação, envie um e-mail <Teamscategorypartner@microsoft.com> .
