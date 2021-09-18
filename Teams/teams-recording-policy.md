---
title: Introdução à Teams gravação baseada em política para & reuniões
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
description: Saiba mais sobre Teams gravação baseada em política para & reuniões
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
ms.openlocfilehash: a6e154f6e972fe54c29f8fcded8c554bf8893795
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432273"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Introdução Teams gravação baseada em política para & reuniões

O registro baseado em política permite que as organizações que adotam o Microsoft Teams para chamadas e reuniões estipulem, usando uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante.

O Teams foi aprimorado para oferecer suporte à integração de soluções de gravação de terceiros, incluindo a funcionalidade da plataforma, as experiências do usuário e as interfaces administrativas necessárias para fornecer uma solução de ponta a ponta para configurar, gerenciar, gravar, armazenar e analisar as comunicações Teams. Os aprimoramentos incluem APIs e eventos da plataforma de comunicações para gravação, que fornece:

- Captura de mídia perfeita e de alta qualidade em todos os dispositivos e todos os pontos de extremidade com suporte para áudio, vídeo, compartilhamento de tela e chat.

- Suporte para captura de interação entre Teams usuários e pontos de extremidade de chamada com suporte (Teams, Teams Mobile, Skype for Business, PSTN)

- Novas políticas administrativas para registro de conformidade, incluindo a integração com as Teams de reunião e ferramentas e políticas administrativas existentes

O Registro de Conformidade pode ser habilitado em usuários Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5. 

Os recursos de integração da solução de registro de conformidade também foram revisados no Ignite 2019 na sessão Registro de Conformidade e Microsoft Teams [de conformidade.](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Teams visão geral da gravação de interação

Os casos de uso do registro de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação – Conveniência, Funcional, Organizacional e Interceptação Legal, conforme mostrado na imagem:

> [!div class="mx-imgBorder"]
> ![Captura de tela mostrando a interação registrando o que e por quê.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")

Cada uma das categorias envolve requisitos diferentes para como as gravações são iniciadas, o que é gravado, onde as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é manipulada.

| Tipo                   | Conveniência (gravação Teams regular) | Org - Regulamentado (Registro de Conformidade) |
| ---------------------- | ------------------ | --------------- |
| Iniciador              | Usuário               | Administrador (sistema)  |
| Destino                 | Por chamada/reunião | Por usuário        |
| Armazenamento proprietário          | Usuário               | Conformidade      |
| Notificação necessária? | Sim                | Sim             |
| Proprietário do Access           | Usuário               | Conformidade      |
| Política de Retenção?      | Opcional           | Sim             |

Teams oferece vários recursos para [registro](./cloud-recording.md) prático e funcional de reuniões e eventos ao vivo. O registro organizacional significa permitir que as organizações que adotam o Teams para chamadas e reuniões estipulem, por meio de uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante. Os usuários sob essa política estarão cientes de que suas interações digitais com o Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação depois que a interação for concluída. A gravação torna-se parte do arquivo morto organizacional disponível para conformidade e equipe jurídica para Descoberta e Descoberta, retenção legal e outros usos de retenção corporativa.

## <a name="example-user-needs"></a>Exemplo de necessidades do usuário

<table>
<thead>
<tr class="header">
<th>Pessoal</th>
<th>Necessidades</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Usuários registrados</td>
<td><ul>
<li><p>Seja notificado quando a gravação estiver em andamento.</p></li>
<li><p>Seja informado quando o erro de política e/ou gravador está causando alterações no comportamento de chamada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrador de comunicações</td>
<td><ul>
<li><p>Entenda por que e como aplicar/impor políticas de gravação Teams usuários/pontos de extremidade.</p></li>
<li><p>Configure e mantenha Teams de gravação para a organização.</p></li>
<li><p>Monitore e solucione problemas relacionados à gravação com Teams chamadas e reuniões.</p></li>
<li><p>Suporte ao responsável pela conformidade interna com análises operacionais sobre uso, qualidade e confiabilidade.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsável pela conformidade</td>
<td><ul>
<li><p>Colete todas as Teams comunicações da maneira necessária para cumprir as obrigações de conformidade nos limites regionais apropriados.</p></li>
<li><p>Pesquise interações com base em metadados relacionados à comunicação ou conteúdo de interação. Exemplos comuns incluem:</p>
<ul>
<li><p><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados comerciais personalizados</p></li>
<li><p><strong>Conteúdo</strong> – Transcrição, sentimento, phonetics, interações relacionadas</p></li>
</ul></li>
<li><p>Analise e interaja com comunicações coletadas, incluindo a capacidade de monitorar interações enquanto elas estão sendo coletadas.</p></li>
<li><p>Garantir a segurança das comunicações coletadas e impedir a adulteração em todos os estágios.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Visão geral da arquitetura de soluções

As soluções de registro de conformidade são integradas Teams conforme mostrado no diagrama a seguir:

> [!div class="mx-imgBorder"]
> ![Captura de tela mostrando a configuração do aplicativo personalizado da equipe.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma Teams ou chamada é enviada e recebida.")

## <a name="recorder"></a>Gravador

O componente principal da solução de registro de conformidade é o gravador.
Os gravadores são construídos como serviços dimensionáveis baseados no Azure (bots) que usam a plataforma de comunicações da [Microsoft](/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph. O gravador fornece a interação direta com as [APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) da plataforma de comunicações Teams reuniões e fornece o ponto de extremidade para ingestão de mídia.

Um [aplicativo de gravador de conformidade](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) de exemplo está disponível que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade. O exemplo também tem exemplos sobre o uso [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) da API para gravar interações específicas, como manipular o roteamento de chamadas de [entrada,](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)alterar estados de gravação e remover o usuário que está [sendo gravado](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph documentação sobre APIs específicas pode ser encontrada aqui para [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) e [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).

A implementação exata do serviço de gravador varia de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para alcançar alta disponibilidade e distribuição geográfica da implantação para reduzir a latência de Teams para o gravador. Além disso, é esperado que os próprios Gravadores sejam projetados com resiliência e redundância em mente.

Os parceiros devem confirmar a versão de versão mínima necessária das APIs e SDKs de comunicações do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de registro de conformidade sejam suportados.

Dois requisitos específicos que são fundamentais para o cenário de registro de conformidade são:

- O bot do gravador deve ser implantado no Azure

- O bot do gravador deve ser executado em uma Windows VM no Azure

Os requisitos do Azure e Windows VM aplicam-se apenas ao componente bot do Teams, o que significa que um parceiro pode implementar o restante da plataforma de sua escolha, desde que possa atender aos requisitos funcionais e de desempenho relevantes para o registro de conformidade.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Atribuição e provisionamento da política de registro de conformidade

Os administradores de IT podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de registro de conformidade. Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando uma interação de comunicação ocorre. As políticas de registro de conformidade são gerenciadas usando [o Microsoft PowerShell](./teams-powershell-overview.md) e podem ser aplicadas no nível de locatário, por usuário e grupo de segurança para cada organização. Você pode encontrar mais informações sobre as políticas do Microsoft Docs for [Meeting,](./meeting-policies-in-teams.md) [políticas de chamada](./teams-calling-policy.md) e políticas de [grupo.](./assign-policies.md#assign-a-policy-to-a-group)

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

2. Criar uma política de Registro de Conformidade.

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

   Consulte [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).

3. Atribua a política de Registro de Conformidade a um usuário.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Consulte [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Experiências do usuário

O suporte para notificações é habilitado usando as experiências Teams cliente. As experiências podem ser visuais ou de áudio.

**Teams clientes - aviso visual**
- Área de trabalho/web
- Mobile (iOS/Android)
- Teams telefones
- Teams salas

**Outros pontos de extremidade - aviso de áudio**
- Telefones SIP
- Skype for Business
- Audioconferência
- Chamadores PSTN

> [!NOTE]
> O Registro de Conformidade não é suportado com filas de chamada do modo conferência. Use filas de chamada do modo de transferência.

## <a name="compliance-recording-for-teams-certification-programs"></a>Registro de conformidade para Teams de certificação

Além de publicar APIs disponíveis publicamente, permitindo que os parceiros desenvolvam e integrem soluções CCaaS com o Teams, desenvolvemos o registro de conformidade para o programa de certificação do Microsoft Teams para fornecer aos clientes a garantia de que a solução de cada parceiro participante foi testada e verificada para fornecer a qualidade, compatibilidade e confiabilidade esperadas das soluções da Microsoft.  

Os parceiros a seguir certificados sua solução para Microsoft Teams.<br/><br/>

|Parceiro|Site da solução |
|:--|:--|
|Tecnologias ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Selador |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Caixa Vermelha |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<br/>
Os parceiros a seguir estão no processo de certificar sua solução para Microsoft Teams.<br/><br/>

|Parceiro|Site da solução |
|:--|:--|
|Tecnologia perspicaz |[http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/](http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/) |
|Tecnologias Landis |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Inovação de Carvalho |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |

Essa lista será atualizada à medida que mais parceiros ingressarem e atenderem aos critérios de certificação.

## <a name="next-steps"></a>Próximas etapas

Se você for um fornecedor que está tentando ingressar no programa de certificação, envie emails [para](mailto:Teamscategorypartner@microsoft.com)Teamscategorypartner@microsoft.com .
