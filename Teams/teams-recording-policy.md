---
title: Introdução à gravação baseada em políticas do Teams para chamadas & reuniões
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre a gravação baseada em políticas do Teams para chamadas & reuniões
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
ms.openlocfilehash: b23430398e213c7df9fcd72ccb9d32f88ee1ed1f
ms.sourcegitcommit: 0592f9d2696fe8c840a4ed3e7f99e55ca0c9c3e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67418480"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introdução à gravação baseada em políticas do Teams para chamadas & reuniões

A gravação baseada em políticas permite que as organizações que adotam o Microsoft Teams para chamadas e reuniões estipulem, usando uma política administrativa, quando chamadas e reuniões online devem ser registradas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante.

O Teams foi aprimorado para dar suporte à integração de soluções de gravação de terceiros, incluindo a funcionalidade da plataforma, as experiências do usuário e as interfaces administrativas necessárias para fornecer uma solução de ponta a ponta para configurar, gerenciar, gravar, armazenar e analisar as comunicações do Teams. Os aprimoramentos incluem APIs e eventos da plataforma de comunicações para gravação, que fornecem:

- Captura de mídia contínua e de alta qualidade em todos os dispositivos e todos os pontos de extremidade com suporte para áudio, vídeo, compartilhamento de tela e chat.

- Suporte para captura de interação entre usuários do Teams e pontos de extremidade de chamada com suporte (Teams, Teams Mobile, Skype for Business, PSTN)

- Novas políticas administrativas para registro de conformidade, incluindo integração com ferramentas e políticas de reunião e chamadas administrativas existentes do Teams

A Gravação de Conformidade pode ser habilitada em Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5. 

As funcionalidades de integração da solução de gravação de conformidade também foram revisadas no Ignite 2019 na gravação de conformidade e [na sessão do Microsoft Teams](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>Visão geral da gravação de interação do Teams

Os casos de uso de gravação de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação – Conveniência, Funcional, Organizacional e Interceptação Legal, conforme mostrado na imagem:

> [!div class="mx-imgBorder"]
> ![Captura de tela mostrando o motivo e o motivo da gravação da interação.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")

Cada uma das categorias envolve requisitos diferentes de como as gravações são iniciadas, o que é registrado, onde as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é tratada.

| Tipo                   | Conveniência (gravação regular do Teams) | Organização - Regulamentado (Registro de Conformidade) |
| ---------------------- | ------------------ | --------------- |
| Iniciador              | Usuário               | Administração (sistema)  |
| Destino                 | Por chamada/reunião | Por usuário        |
| Proprietário do armazenamento          | Usuário               | Conformidade      |
| Notificação necessária? | Sim                | Sim             |
| Proprietário do Access           | Usuário               | Conformidade      |
| Política de Retenção?      | Opcional           | Sim             |

O Teams fornece vários recursos [para gravação](./cloud-recording.md) funcional e conveniente de reuniões e eventos ao vivo. A gravação organizacional significa permitir que as organizações que adotam o Teams para chamadas e reuniões estipulem, por meio de uma política administrativa, quando chamadas e reuniões online devem ser registradas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante. Os usuários sob essa política estarão cientes de que suas interações digitais com o Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação depois que a interação for concluída. A gravação torna-se parte do arquivo organizacional disponível para conformidade e pessoal jurídico para Descoberta Eletrônica, retenção legal e outros usos de retenção corporativa.

## <a name="example-user-needs"></a>Exemplo de necessidades do usuário

<table>
<thead>
<tr class="header">
<th>Pessoal</th>
<th>Precisa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuários registrados</td>
<td><ul>
<li><p>Seja notificado quando a gravação estiver em andamento.</p></li>
<li><p>Seja informado quando o erro de política e/ou gravador estiver causando alterações no comportamento de chamada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicações</td>
<td><ul>
<li><p>Entenda por que e como aplicar/impor políticas de gravação a usuários/pontos de extremidade do Teams.</p></li>
<li><p>Configure e mantenha as políticas de gravação do Teams para a organização.</p></li>
<li><p>Monitore e solucione problemas relacionados à gravação com chamadas e reuniões do Teams.</p></li>
<li><p>Suporte ao responsável pela conformidade interna com análise operacional sobre uso, qualidade e confiabilidade.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsável pela conformidade</td>
<td><ul>
<li><p>Colete todas as comunicações do Teams da maneira necessária para atender às obrigações de conformidade nos limites regionais apropriados.</p></li>
<li><p>Pesquise interações com base em metadados relacionados à comunicação ou conteúdo de interação. Exemplos comuns incluem:</p>
<ul>
<li><p><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados corporativos personalizados</p></li>
<li><p><strong>Conteúdo</strong> – Transcrição, sentimento, fonética, interações relacionadas</p></li>
</ul></li>
<li><p>Analise e interaja com as comunicações coletadas, incluindo a capacidade de monitorar as interações conforme elas estão sendo coletadas.</p></li>
<li><p>Garantir a segurança das comunicações coletadas e evitar adulteração em todos os estágios.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Visão geral da arquitetura da solução

As soluções de gravação de conformidade são integradas ao Teams, conforme mostrado no diagrama a seguir:

> [!div class="mx-imgBorder"]
> ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma reunião ou chamada do Teams é enviada e recebida.")

> [!NOTE]
> Essa solução foi projetada especificamente para habilitar a gravação de conformidade baseada em políticas com o Teams. Não haverá suporte para qualquer outro uso dessa solução.

## <a name="recorder"></a>Gravador

O componente principal da solução de gravação de conformidade é o gravador.
Os gravadores são criados como serviços escalonáveis baseados no Azure (bots) que usam a plataforma de comunicações da [Microsoft](/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph. O gravador fornece a interação direta com as [APIs](/graph/api/resources/communications-api-overview) da plataforma de comunicação de reuniões e chamadas do Teams e fornece o ponto de extremidade para ingestão de mídia.

Um [aplicativo de gravador de conformidade](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) de exemplo está disponível que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade. O exemplo também tem exemplos sobre o uso da API para registrar interações específicas[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244), como lidar com o roteamento de chamadas de [entrada, alterar](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) os estados de gravação e remover o usuário que [está sendo gravado](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
A documentação do Graph sobre as APIs específicas pode ser encontrada aqui para [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) e [incomingContext](/graph/api/resources/incomingcontext).

A implementação exata do serviço de gravador varia de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para obter alta disponibilidade e distribuição geográfica da implantação para reduzir a latência do Teams para o gravador. Além disso, espera-se que os próprios Gravadores sejam projetados com resiliência e redundância em mente.

Os parceiros devem confirmar a versão de lançamento mínima necessária das APIs de comunicações e SDKs do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de gravação de conformidade sejam compatíveis.

Dois requisitos específicos que são fundamentais para o cenário de registro de conformidade são:

- O bot do Gravador deve ser implantado no Azure

- O bot do Gravador deve ser executado em uma VM do Windows no Azure

Os requisitos de VM do Windows e do Azure se aplicam somente ao componente bot do Teams, o que significa que um parceiro pode implementar o restante da plataforma de sua escolha, desde que possa atender aos requisitos funcionais e de desempenho relevantes para o registro de conformidade.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Provisionamento e atribuição de política de gravação de conformidade

Os administradores de TI podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de gravação de conformidade. Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando ocorre uma interação de comunicação. As políticas de registro de conformidade são gerenciadas usando [o Microsoft PowerShell](./teams-powershell-overview.md) e podem ser aplicadas no nível de locatário, por usuário e grupo de segurança para cada organização. Você pode encontrar mais informações sobre o Microsoft Docs para políticas de [reunião](./meeting-policies-overview.md), [políticas de chamada](./teams-calling-policy.md) e [políticas de grupo](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

1. Crie uma instância de aplicativo em seu locatário.

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

2. Crie uma política de Gravação de Conformidade.

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

   Consulte [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Atribua a política de Gravação de Conformidade a um usuário.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Consulte [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Experiências do usuário

O suporte para notificações é habilitado usando as experiências de cliente do Teams. As experiências podem ser visuais ou de áudio.

**Clientes do Teams – aviso visual**
- Área de trabalho/web
- Móvel (iOS/Android)
- Telefones do Teams
- Salas do Teams

**Outros pontos de extremidade – aviso de áudio**
- Telefones SIP
- Skype for Business
- Audioconferência (aviso de áudio no idioma padrão do número de discagem ou selecionado pelo usuário)
- Chamadores PSTN (aviso de áudio no idioma padrão do usuário do Teams)

> [!NOTE]
> Não há suporte para a Gravação de Conformidade com filas de chamadas no modo conferência. Use filas de chamadas do modo de transferência.
> A Gravação de Conformidade não funcionará se os usuários tiverem tido uma interrupção na Internet e estão fazendo e recebendo chamadas PSTN usando um SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Registro de conformidade para programas de certificação do Teams

Além de publicar APIs publicamente disponíveis, permitindo que os parceiros desenvolvam e integrem soluções CCaaS com o Teams, desenvolvemos a gravação de conformidade para o programa de certificação do Microsoft Teams para fornecer aos clientes a garantia de que a solução de cada parceiro participante foi testada e verificada para fornecer a qualidade, a compatibilidade e a confiabilidade esperadas das soluções da Microsoft.  

Os parceiros a seguir certificam sua solução para o Microsoft Teams.<br/><br/>

|Parceiro|Site da solução |
|:--|:--|
|Tecnologias ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dublador |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Tecnologia insightful |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Caixa Vermelha |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Lago Theta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Os parceiros a seguir estão no processo de certificar sua solução para o Microsoft Teams.<br/><br/>

|Parceiro|Site da solução |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Soluções Mida |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


Essa lista será atualizada à medida que mais parceiros ingressarem e atenderem aos critérios de certificação.


## <a name="next-steps"></a>Próximas etapas

Se você for um fornecedor que busca ingressar no programa de certificação, preencha [esse formulário](https://aka.ms/CallingPlatformIntake) como a próxima etapa. Se você precisar fornecer mais contexto e detalhes, envie um [email para Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
