---
title: Introdução à gravação baseada em políticas de equipe para fazer chamadas & reuniões
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre a gravação baseada em políticas de equipe para fazer chamadas & reuniões
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc09323e7f0a25f0f7c7083307776ad1a08bf4fb
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294046"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introdução à gravação baseada em políticas de equipe para chamadas & reuniões

A gravação baseada em políticas permite que as organizações que adotarem o Microsoft Teams para fazer chamadas e reuniões sejam exigidas, usando uma política administrativa, quando chamadas e reuniões online devem ser automaticamente gravadas e capturadas para processamento e retenção subsequentes, conforme exigido pela política corporativa ou normativa pertinente.

O Microsoft Teams foi aprimorado para dar suporte à integração de soluções de gravação de terceiros, incluindo funcionalidade da plataforma, experiências do usuário e interfaces administrativas necessárias para fornecer uma solução completa para a configuração, o gerenciamento, a gravação, o armazenamento e a análise de comunicações do teams. Isso inclui APIs e eventos de plataforma de comunicações para gravação, o que fornece:

- Captura de mídia de alta qualidade e contínua entre dispositivos e todos os pontos de extremidade compatíveis para áudio, vídeo, compartilhamento de tela e chat.

- Suporte para captura de interação entre usuários do Teams e pontos de extremidade com suporte (Teams, Mobile Teams, Skype for Business, PSTN)

- Novas políticas administrativas para a gravação de conformidade, incluindo a integração com as ferramentas de reunião e as ferramentas de reunião e as políticas de reunião existentes

- Habilitado para usuários do teams com uma licença separada

Os recursos de integração da solução de gravação de conformidade também foram revisados em Ignite 2019 na [<span class="underline">sessão de gravação de conformidade e Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).

## <a name="teams-interaction-recording-overview"></a>Visão geral da gravação de interação do teams

Casos de uso de gravação de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação – conveniência, funcional, organizacional e interceptação legal, conforme mostrado na imagem:

![Captura de tela mostrando a interação gravando o que e por quê.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")

Cada uma das categorias envolve diferentes requisitos para a forma como as gravações são iniciadas, o que é gravado, em que as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é manipulada.

|                        | Transtorno        | Funcional         | Org-geral      | Regulamentado pela organização | Interceptação legal   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| Inicia              | Usuário               | Aplicativo/solução       | Administrador (sistema)     | Administrador (sistema)  | LEA                |
| Destino                  | Por chamada/reunião | Por chamada/reunião | Por chamada/reunião | Por usuário        | Por ponto de extremidade/DID |
| Proprietário do armazenamento          | Usuário               | AppV                | Locatário              | Conformidade      | LEA                |
| É preciso fornecer uma notificação? | Sim                 | Sim                 | Sim                 | Sim             | Não                 |
| Proprietário do Access           | Usuário               | AppV                | Locatário              | Conformidade      | LEA                |
| Política de retenção?      | Opcional           | Sim                 | Sim                 | Sim              | Sim                |

O Microsoft Teams oferece vários recursos para gravação [<span class="underline">conveniente</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) e funcional para reuniões e eventos ao vivo. A gravação organizacional significa permitir que as organizações que adotarem equipes para chamadas e reuniões sejam estipuladas, por meio de uma política administrativa, quando chamadas e reuniões online devem ser automaticamente registradas e capturadas para processamento e retenção subsequentes, conforme a necessidade de uma política corporativa ou normativa relevante. Os usuários desta política ficarão cientes de que suas interações digitais com o Microsoft Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação após a conclusão da interação. A gravação torna-se parte do arquivo organizacional disponível para a conformidade e o pessoal legal para eDiscovery, o controle legal e outros usos corporativos de retenção.

## <a name="example-user-needs"></a>Exemplo de necessidades do usuário

<table>
<thead>
<tr class="header">
<th><strong>Pessoal</strong></th>
<th><strong>Deve</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuários registrados</td>
<td><ul>
<li><p>Seja notificado quando a gravação estiver em andamento.</p></li>
<li><p>Seja informado quando o erro de política e/ou gravador estiver causando alterações no comportamento de chamadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicações</td>
<td><ul>
<li><p>Entender por que e como aplicar/impor políticas de gravação a usuários/pontos de extremidade da equipe.</p></li>
<li><p>Configurar e manter políticas de gravação de equipes para a organização.</p></li>
<li><p>Monitorar e solucionar problemas relacionados à gravação com chamadas e reuniões do teams.</p></li>
<li><p>Suporte ao responsável pela conformidade interna com análises operacionais sobre uso, qualidade e confiabilidade.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsável pela conformidade</td>
<td><ul>
<li><p>Reúna todas as comunicações de equipes da maneira necessária para atender obrigações de conformidade em limites regionais apropriados.</p></li>
<li><p>Pesquisar interações com base em conteúdo de interação ou metadados relacionados à comunicação. Exemplos comuns incluem:</p>
<ul>
<li><p><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados corporativos personalizados</p></li>
<li><p><strong>Conteúdo</strong> – transcrição, refira, fonética, interações relacionadas</p></li>
</ul></li>
<li><p>Analise e interaja com comunicações coletadas, incluindo a capacidade de monitorar interações à medida que elas são coletadas.</p></li>
<li><p>Garanta a segurança das comunicações coletadas e impeça a violação em todos os estágios.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Visão geral da arquitetura da solução

As soluções de gravação de conformidade são integradas ao Teams, conforme mostrado no diagrama a seguir:

![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma reunião ou uma chamada de equipe é enviada e recebida.")

## <a name="recorder"></a>Gravador

O componente principal da solução de gravação de conformidade é o gravador.
Os gravadores são criados como serviços baseados no Azure escaláveis (bots) que [<span class="underline">aproveitam a plataforma de comunicações da Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph. O gravador fornece a interação direta com as APIs de plataforma de [<span class="underline">comunicação de comunicações</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) e as chamadas de equipe e fornece o ponto de extremidade para inclusão de mídia.

Um [<span class="underline">aplicativo de gravador de conformidade de exemplo está disponível</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade. O exemplo também tem exemplos sobre o uso da API para gravar interações específicas, como manipular o roteamento de [<span class="underline">chamadas recebidas</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , [<span class="underline">alterar os Estados de gravação</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)e [<span class="underline">remover o usuário que está sendo gravado</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
A documentação de gráficos sobre APIs específicas pode ser encontrada aqui para [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) e [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).

A implementação exata do serviço de gravador varia de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para obter alta disponibilidade e distribuição geográfica da implantação para reduzir a latência do teams para o gravador. Além disso, espera-se que os gravadores sejam projetados com resiliência e redundância em mente.

Os parceiros devem confirmar a versão mínima necessária de lançamento das APIs e SDKs de comunicação do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de gravação de conformidade sejam compatíveis.

Dois requisitos específicos que são fundamentais para o cenário de gravação de conformidade são:

- O bot do gravador deve ser implantado no Azure

- O bot de gravador deve ser executado em uma VM do Windows no Azure

Os requisitos do Azure e da VM do Windows se aplicam somente ao componente bot do Teams, o que significa que um parceiro pode implementar o restante da plataforma de sua preferência, que pode atender aos requisitos de desempenho e funcionamento relevantes para a gravação de conformidade.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Conformidade de atribuição e provisionamento de política de gravação

Os administradores de ti podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de gravação de conformidade. Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando ocorre uma interação de comunicação. As políticas de gravação de conformidade são gerenciadas usando o [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) e podem ser aplicadas no locatário e no nível de cada usuário para cada organização. Você pode encontrar mais informações sobre documentos da Microsoft para [<span class="underline">políticas de reunião</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) e políticas de [<span class="underline">chamadas</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).

1. Crie uma instância do aplicativo em seu locatário.

```powershell
PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
UserPrincipalName : cr.instance@contoso.onmicrosoft.com
ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
DisplayName       : ComplianceRecordingBotInstance
PhoneNumber       :
```

```powershell
PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
```

2. Crie uma política de gravação de conformidade.

```powershell
PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

Identity                        : Global
ComplianceRecordingApplications : {}
Enabled                         : True
WarnUserOnRemoval               : True
Description                     : Test policy created by tenant admin
```

```powershell
PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
-ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Atribua a política de gravação de conformidade a um usuário.

```powershell
PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

```powershell
PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

UserPrincipalName              : testuser@contoso.onmicrosoft.com
TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
```

## <a name="user-experiences"></a>Experiências do usuário

O suporte para notificações está habilitado com o uso das experiências do cliente das equipes. As experiências podem ser visuais ou de áudio.

**Clientes do teams – aviso Visual**
- Área de trabalho/Web
- Celular (iOS/Android)
- Telefones de equipes
- Salas de equipe

**Outros pontos de extremidade-aviso de áudio**
- Telefones SIP
- Skype for Business
- Audioconferência
- Chamadores PSTN

## <a name="compliance-recording-for-teams-certification-programs"></a>Registro de conformidade para programas de certificação de equipes

Além de publicar as APIs publicamente disponíveis, permitindo que os parceiros desenvolvam e integrem soluções do CCaaS com o Teams, desenvolvemos o programa de certificação de conformidade para o Microsoft Teams para fornecer aos clientes a garantia de que cada parceiro participante tenha sido testado e verificado para fornecer a qualidade, a compatibilidade e a confiabilidade esperados pelas soluções da Microsoft.  

Os parceiros a seguir estão no processo de certificação da solução para o Microsoft Teams.  

|Sócio|Site da solução |
|:--|:--|
|Tecnologias ASC |[https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html](https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Bom |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Caixa vermelha |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Esta lista será atualizada à medida que mais parceiros entrarem e atenderem aos critérios de certificação.

## <a name="next-steps"></a>Próximas etapas

Se você for um fornecedor que está procurando participar do programa de certificação, envie um email para <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>
