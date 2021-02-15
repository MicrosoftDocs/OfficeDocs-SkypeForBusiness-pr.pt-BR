---
title: Introdução à Gravação baseada em política do Teams para & Reuniões
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre a Gravação baseada em política do Teams para & Reuniões
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
ms.openlocfilehash: 2d8949a4eaa3365857768726a523ae480a94df55
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196765"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introdução à gravação baseada em política do Teams para & reuniões

A gravação baseada em política permite que as organizações que adotam o Microsoft Teams para chamadas e reuniões sejam desalobiladas, usando uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido por uma política corporativa ou regulatória relevante.

O Teams foi aprimorado para oferecer suporte à integração de soluções de gravação de terceiros, incluindo a funcionalidade da plataforma, as experiências do usuário e as interfaces administrativas necessárias para fornecer uma solução de ponta a ponta para configurar, gerenciar, gravar, armazenar e analisar comunicações do Teams. Os aprimoramentos incluem APIs da plataforma de comunicações e eventos para gravação, que fornece:

- Captura de mídia perfeita e de alta qualidade em todos os dispositivos e todos os pontos de extremidade compatíveis com áudio, vídeo, compartilhamento de tela e chat.

- Suporte para captura de interação entre usuários do Teams e pontos de extremidade de chamadas com suporte (Teams, Teams Mobile, Skype for Business, PSTN)

- Novas políticas administrativas para gravação de conformidade, incluindo integração com as ferramentas e políticas administrativas e de reunião existentes do Teams

A Gravação de Conformidade pode ser habilitada para usuários do Microsoft 365 A3/A5/E3/E5/Business Premium e office 365 A3/A5/E3/E5. 

Os recursos de integração da solução de gravação de conformidade também foram revisados no Ignite 2019 na sessão gravação de [<span class="underline">conformidade e no Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Visão geral da gravação de interação do Teams

Os casos de uso de gravação de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação : Conveniência, Funcional, Organizacional e Interceptação Legal, conforme mostrado na imagem:

![Captura de tela mostrando a interação gravando o que e por quê.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")

Cada uma das categorias exige requisitos diferentes de como as gravações são iniciadas, o que é gravado, onde as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é tratada.

| Tipo                   | Conveniência (Gravação regular do Teams) | Organização – Regulamentada (Gravação de Conformidade) |
| ---------------------- | ------------------ | --------------- |
| Iniciador              | Usuário               | Administrador (sistema)  |
| Destino                  | Por chamada/reunião | Por usuário        |
| Proprietário do armazenamento          | Usuário               | Conformidade      |
| Notificação necessária? | Sim                | Sim             |
| Proprietário do Access           | Usuário               | Conformidade      |
| Política de Retenção?      | Opcional           | Sim             |

O Teams fornece vários recursos para [<span class="underline">gravação prática</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) e funcional para reuniões e eventos ao vivo. A gravação organizacional significa permitir que as organizações que adotam o Teams para chamadas e reuniões sejam desaloadas, por meio de uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido por uma política corporativa ou regulatória relevante. Os usuários sob essa política estarão cientes de que suas interações digitais com o Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação assim que a interação for concluída. A gravação torna-se parte do arquivo morto organizacional disponível para conformidade e pessoal jurídico para Descobertas EDiscovery, retenção legal e outros usos de retenção corporativa.

## <a name="example-user-needs"></a>Exemplo de necessidades do usuário

<table>
<thead>
<tr class="header">
<th><strong>Pessoal</strong></th>
<th><strong>Precisa</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuários registrados</td>
<td><ul>
<li><p>Seja notificado quando a gravação estiver em andamento.</p></li>
<li><p>Mantenha-se informado quando o erro de política e/ou gravador está causando alterações no comportamento da chamada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicações</td>
<td><ul>
<li><p>Entenda por que e como aplicar/impor políticas de gravação aos usuários/pontos de extremidade do Teams.</p></li>
<li><p>Configure e mantenha as políticas de gravação do Teams para a organização.</p></li>
<li><p>Monitore e solucione problemas relacionados à gravação com chamadas e reuniões do Teams.</p></li>
<li><p>Suporte ao responsável pela conformidade interna com análises operacionais sobre uso, qualidade e confiabilidade.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsável pela conformidade</td>
<td><ul>
<li><p>Colete todas as comunicações do Teams da maneira necessária para atender às obrigações de conformidade nos limites regionais apropriados.</p></li>
<li><p>Pesquise interações com base em metadados relacionados à comunicação ou conteúdo de interação. Exemplos comuns incluem:</p>
<ul>
<li><p><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados comerciais personalizados</p></li>
<li><p><strong>Conteúdo</strong> – Transcrição, sentimentos, phoneética, interações relacionadas</p></li>
</ul></li>
<li><p>Analise e interaja com comunicações coletadas, incluindo a capacidade de monitorar as interações à medida que elas são coletadas.</p></li>
<li><p>Garanta a segurança das comunicações coletadas e impeça a adulteração em todos os estágios.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Visão geral da arquitetura de soluções

As soluções de gravação de conformidade são integradas ao Teams, conforme mostrado no diagrama a seguir:

![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma reunião ou chamada do Teams é enviada e recebida.")

## <a name="recorder"></a>Gravador

O componente principal da solução de gravação de conformidade é o gravador.
Os gravadores são feitos como serviços escaláveis baseados no Azure (bots) que utilizam a plataforma de comunicações da [<span class="underline">Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph. O gravador fornece a interação direta com as [<span class="underline">APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) da plataforma de comunicações de chamadas e reuniões do Teams e fornece o ponto de extremidade para ingestão de mídia.

Um [<span class="underline">aplicativo gravador de conformidade</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) de exemplo está disponível que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade. O exemplo também tem exemplos sobre o uso [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) da API para registrar interações específicas, como lidar com o roteamento de chamadas de [<span class="underline">entrada,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)alterar os estados de gravação e remover o usuário que está [<span class="underline">sendo gravado.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
A documentação do gráfico nas APIs específicas pode ser encontrada aqui para [<span class="underline">atualizarRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) e [<span class="underline">incomingContext.</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)

A implementação exata do serviço gravador variará de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para alcançar a alta disponibilidade e a distribuição geográfica da implantação para reduzir a latência do Teams para o gravador. Além disso, espera-se que os próprios Gravadores sejam projetados com resiliência e redundância em mente.

Os parceiros devem confirmar a versão mínima necessária das APIs e SDKs de comunicações do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de gravação de conformidade sejam suportados.

Dois requisitos específicos que são fundamentais para o cenário de gravação de conformidade são:

- O bot gravador deve ser implantado no Azure

- O bot gravador deve ser executado em um VM do Windows no Azure

Os requisitos do Azure e do Windows VM aplicam-se apenas ao componente do Bot do Teams, o que significa que um parceiro pode implementar o restante da plataforma de sua escolha, desde que possa atender aos requisitos funcionais e de desempenho relevantes para o registro de conformidade.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Provisionamento e atribuição de política de gravação de conformidade

Os administradores de IT podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de gravação de conformidade. Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando ocorre uma interação de comunicação. As políticas de gravação de conformidade são gerenciadas usando [<span class="underline">o Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) e podem ser aplicadas no nível do locatário, do usuário e do grupo de segurança de cada organização. Você pode encontrar mais informações [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)sobre políticas [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) de reunião, políticas de chamada e políticas [<span class="underline">de grupo</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)do Microsoft Docs.

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

2. Criar uma política de Gravação de Conformidade.

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Atribua a política de Gravação de Conformidade a um usuário.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Experiências do usuário

O suporte para notificações está habilitado usando as experiências de cliente do Teams. As experiências podem ser visuais ou de áudio.

**Clientes do Teams – aviso visual**
- Área de trabalho/web
- Celular (iOS/Android)
- Telefones do Teams
- Salas do Teams

**Outros pontos de extremidade - aviso de áudio**
- Telefones SIP
- Skype for Business
- Audioconferência
- Chamadores PSTN

## <a name="compliance-recording-for-teams-certification-programs"></a>Gravação de conformidade para programas de certificação do Teams

Além de publicar APIs publicamente disponíveis, permitindo que os parceiros desenvolvam e integrem soluções CCaaS com o Teams, desenvolvemos a gravação de conformidade para o programa de certificação do Microsoft Teams para fornecer aos clientes a garantia de que a solução de cada parceiro participante foi testada e verificada para fornecer a qualidade, a compatibilidade e a confiabilidade esperadas das soluções da Microsoft.  

Os seguintes parceiros certificaram sua solução para o Microsoft Teams.

|Parceiro|Site de solução |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Bom |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


Os seguintes parceiros estão em processo de certificação de sua solução para o Microsoft Teams.

|Parceiro|Site de solução |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Númúm |[https://numonix.cloud](https://numonix.cloud)    |
|Inovação com a Empresa |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Caixa Vermelha |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Essa lista será atualizada à medida que mais parceiros ingressarem e atenderem aos critérios de certificação.

## <a name="next-steps"></a>Próximas etapas

Se você for um fornecedor que está tentando ingressar no programa de certificação, <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a>
