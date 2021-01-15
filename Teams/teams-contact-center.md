---
title: Central de Contatos do Teams
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
ms.openlocfilehash: e48cac3e556c6bb99e29ad07f3d875362ad42489
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820991"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Integrações do Contact Center para o Microsoft Teams

A integração de soluções populares do centro de contatos com o Microsoft Teams é uma necessidade comum dos clientes que implantam recursos de Chamada do Teams.  Este artigo fornece uma visão geral de como as soluções do centro de contatos podem ser integradas ao Microsoft Teams e informações adicionais sobre as soluções parceiras que participam do Programa de Certificação do Centro de Contatos Conectado do Microsoft Teams.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>O que é uma integração do Contact Center para o Microsoft Teams?

Os centros de contatos de hoje oferecem muito mais do que suporte– eles atuam como um dos principais veículos para interação e comentários não filtrados sobre a experiência de um cliente com uma marca. Devido à amplitude dos canais que os clientes de hoje preferem interagir – telefone, email, texto, social – e o volume expandido de pontos de toque associados aos processos de compra atuais, muitas organizações percebiam duas opções adicionais:

1. Cada membro da organização tem o potencial de envolver um cliente diretamente e, portanto, precisa estar equipado com as ferramentas apropriadas.

2. Esse escopo expandido de interações do cliente requer ferramentas que podem ajudar a impulsionar a consistência, o aprimoramento constante e a escala.

O Microsoft Teams oferece suporte a fluxos de trabalho de interação do cliente, atuando como o hub para conexão do cliente interno e externo em seus modos de comunicação, incluindo chat, reuniões de vídeo e chamada. Para algumas empresas, os recursos de voz na nuvem do Microsoft [Teams,](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)incluindo o atendimento [automático](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) e [filas](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)de chamadas, fornecem os recursos e a configuração para atender às suas necessidades.

Para outras pessoas que desejam soluções integradas com ferramentas de negócios e fluxos de trabalho para impulsionar a jornada do cliente, o Microsoft Teams também se integra a alguns dos principais provedores de soluções do Centro de Contatos como Serviço (CCaaS) do setor.

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Centro de Contato Conectado para o Programa de Certificação do Microsoft Teams

As APIs permitem que os parceiros desenvolvam e integrem soluções CCaaS para o Teams. Além disso, desenvolvemos o Centro de Contato Conectado para o Programa de Certificação do Microsoft Teams para fornecer aos clientes a garantia de que a solução de cada parceiro participante foi testada e verificada para fornecer a qualidade, a compatibilidade e a confiabilidade esperadas das soluções da Microsoft.

Os seguintes parceiros estão no processo de certificar sua solução para o Microsoft Teams e estão prontos para envolver os clientes:

|  Parceiro                                                                                                                               |  Site da solução                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `8x8` | https://www.8x8.com/products/integrations/8x8-voice-for-microsoft-teams?locale=us |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | www.contactcenter4all.com |
| `Content Guru` | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| 'Geomant' | https://www.geomant.com/buzzeasy-contact-centre-for-microsoft-teams                                          |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |


Essa lista será atualizada à medida que mais parceiros ingressarem e atenderem aos critérios de certificação.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Como as soluções do centro de contatos funcionam no Microsoft Teams?

O Microsoft Teams oferece uma variedade de recursos para dar suporte ao desenvolvimento de soluções de voz de terceiros, incluindo:

1. [Conectividade de Roteamento Direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [APIs de comunicação na nuvem do Microsoft Graph](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plataforma e extensibilidade do Teams

4. Teams SDKs

Juntos, esses recursos permitem três modelos de integração:

  - **Conectar** (via Roteamento Direto)

  - **Conectar e estender** (Roteamento Direto, APIs do Graph e plataforma de aplicativos do Teams)

  - **Estender e energia** (incorporar SDKs do Teams em aplicativos 3p para interações nativas do Teams)

### <a name="connect"></a>Conectar

Esse modelo conecta parceiros CCaaS à infraestrutura do sistema de telefonia do Microsoft Teams, permitindo roteamento, configuração e insights do sistema aprimorados. Nesse modelo, a solução de parceiro do centro de contatos também pode fornecer serviços de telefonia para números e usuários selecionados.

Agentes que usam soluções criadas no modelo Connect podem coletar informações & informações e, se necessário, transferir chamadas para especialistas no assunto diretamente, usando a presença do SME no Teams para garantir sua disponibilidade.

As organizações podem garantir que as chamadas roteiem para o agente ideal configurando assistentes virtuais automatizados e filas de roteamento baseadas em habilidades.

**Destaques de recursos:**

Embora o seguinte não seja uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - AuthN do Office 365 para agentes permitirem que agentes se conectem ao locatário da Microsoft a partir de seu cliente CCaaS integrado 

  - Indicação de presença dos usuários do Teams 

  - Fluxos de chamadas via Roteamento Direto (conforme indicado nos planos de teste) 

  - Suporte a transferências e chamadas em grupo com usuários do Teams 

  - APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams 

  - Capaz de dar suporte ao tronco SIP de vários locatários para dar suporte a vários clientes no SBC do parceiro.  

  - Parceiros para implementar o [ <span class="underline">SBC (controlador de borda de sessão) certificado pela Microsoft</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Conectar e estender

Esse modelo estende as experiências de funcionários e agentes do centro de contatos integrando-se ao cliente do Teams usando a plataforma cliente [teams,](https://docs.microsoft.com/microsoftteams/platform/overview) [APIs do Teams Graph](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e API de Comunicações na Nuvem no [Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) e usa o sistema de telefonia do Teams para todas as chamadas do centro de contatos e experiências de controle de chamada. Nesse modelo, o parceiro do centro de contatos atua como uma operadora de telefonia junto com o Microsoft 365.

Usando soluções baseadas em Conectar e Estender, os agentes podem se beneficiar de anotações contextuais e dinâmicas correlacionando dados de vários sistemas antes de iniciar uma interação e, em seguida, evitar a troca de contexto custosa trabalhando de forma nativa no Teams para colaboração interna e comunicações externas.

As organizações podem projetar fluxos de trabalho e configurações de roteamento avançadas para o indivíduo e medir a qualidade de seu sistema e interações.

**Destaques de recursos:**

Embora o seguinte não seja uma lista abrangente de recursos para esse modelo de integração, ele realça as principais áreas de foco:

  - APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams 

  - Aplicativo baseado no Teams para experiências de agente 

  - Teams como o ponto de extremidade de chamada principal para os agentes 

  - Cliente do Teams que está chamando todos os controles de chamada

  - O aplicativo de experiência do agente também deve ser capaz de trabalhar na Web do Teams e no cliente móvel

  - Análise, gerenciamento de fluxo de trabalho, experiências baseadas em função para Agentes no aplicativo CCaaS no Teams

  - Experiências de chat e colaboração integradas aos clientes do Teams 

  - Preservar o desempenho e a qualidade das experiências de cliente do Teams em todos os aplicativos  

### <a name="extend-and-power"></a>Estender e energia

Esse modelo permite que os parceiros criem aplicativos de voz nativos baseados no Azure usando a infraestrutura de chamada do Teams e a plataforma de cliente para fornecer soluções modernas e inteligentes para conexão colaborativa de clientes e agentes. O objetivo de Estender e Energia é impulsionar a criatividade do desenvolvedor e impulsionar a produtividade do cliente.

Criando diretamente no Azure, os parceiros podem implantar e provisionar rapidamente sua solução em todas as regiões e regiões geográficas do Teams, beneficiando-se de nossa rede de comunicações global compartilhada enquanto aproveitam o armazenamento, a computação e a análise & serviços cognitivos do Azure.

Com o modelo de integração Extend e Power, os parceiros podem fornecer aos agentes do centro de contatos experiências de comunicação omnicanal, incorporando inteligência artificial para personalizar como e quando os participantes , ou outros serviços, estão envolvidos em uma chamada aplicando a API de Comunicações na Nuvem no [Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).

**Destaques de recursos:**

Embora o seguinte não seja uma lista abrangente de recursos para esse modelo de integração, essas áreas de destaque, além das fornecidas pelo modelo Conectar e Estender.

  - Experiências formais de agente habilitadas de forma nativa para comunicação omnicanal por meio do SDK do Teams 

  - Usar os serviços de colaboração do Teams para colaboração de agentes e interações do cliente  

  - Provisionamento rápido de serviços de nuvem, implantar em qualquer lugar 

  - Controle de conversa direta e interação com usuários durante conversas do Teams 

### <a name="comparing-connected-contact-center-integration-models"></a>Comparando modelos de integração do centro de contatos conectados

Consulte a tabela abaixo para ter uma visão geral dos modelos de integração compatíveis com o Microsoft Teams.

<table>
<thead>
<tr class="header">
<th></th>
<th>Aplicativos de voz do Teams</th>
<th>Conectar</th>
<th>Estender</th>
<th>Energia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modelo de serviço de nuvem</td>
<td>Azure</td>
<td>Parceiro</td>
<td><p>Parceiro +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>Quem opera a solução?</td>
<td>Microsoft</td>
<td>Parceiro</td>
<td>Parceiro</td>
<td>Parceiro</td>
</tr>
<tr class="odd">
<td>Entrar no M365</td>
<td>Sim</td>
<td>Sim</td>
<td>Sim</td>
<td>Sim</td>
</tr>
<tr class="even">
<td>Usuários com a chamada do Teams?</td>
<td>Informal, SME</td>
<td>Informal, SME</td>
<td>Informal, SME, Formal</td>
<td>Informal, SME, Formal</td>
</tr>
<tr class="odd">
<td>Experiência de IW/SME</td>
<td>Teams</td>
<td>Teams</td>
<td><p>Teams +</p>
<p>extensions</p></td>
<td><p>Teams +</p>
<p>extensions</p></td>
</tr>
<tr class="even">
<td>Conectividade de serviço</td>
<td>Plataforma<br />
(Planos de Chamada +DR)</td>
<td>Roteamento direto</td>
<td>Plataforma<br />
(Planos de Chamada + DR)</td>
<td>Plataforma<br />
(Planos de Chamada + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Próximas etapas

Se você for um fornecedor que está tentando ingressar no programa de certificação, envie um <Teamscategorypartner@microsoft.com> email.
