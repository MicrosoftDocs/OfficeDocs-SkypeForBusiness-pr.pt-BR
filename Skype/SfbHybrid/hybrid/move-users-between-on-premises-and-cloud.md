---
title: Mover os usuários entre um ambiente local e a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: em uma implantação local de Skype for Business Server que está habilitada para híbridos, você pode mover os usuários entre o ambiente local e a nuvem.'
ms.openlocfilehash: 5d5f14cfdb5de2e11c95a2532900dfa3fcf669a1
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410702"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover os usuários entre um ambiente local e a nuvem

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Em uma implantação local de Skype for Business Server que está habilitada para híbridos, você pode mover usuários entre o ambiente local e o Teams. Se um usuário está localizado no local ou na nuvem, é conhecido como a página inicial do Skype for Business do usuário:

- Os usuários que estão no local interagem com servidores Skype for Business locais.
- Os usuários que estão em casa online podem interagir com o Teams serviço.

*Teams usuários inerentemente têm uma Skype for Business, quer eles usem Skype for Business ou não.* Se você tiver usuários locais Skype for Business que também estão usando Teams (lado a lado), esses usuários serão ativos no local. Teams usuários com Skype for Business locais não têm a capacidade de interoperar com usuários do Skype for Business de seu cliente Teams, nem podem se comunicar do Teams com usuários em uma organização federada. Essa funcionalidade está totalmente disponível somente depois que o usuário é movido de Skype for Business local para online e se tornou o TeamsOnly. É altamente recomendável que você mova seus usuários para o modo TeamsOnly, o que garantirá que o roteamento de todos os chats e chamadas de entrada caiam em seus clientes Teams cliente. Para obter mais detalhes, [consulte Teams coexistência](/microsoftteams/coexistence-chat-calls-presence) com Skype for Business e diretrizes de migração e [interoperabilidade](/microsoftteams/migration-interop-guidance-for-teams-with-skype)para organizações que usam Teams em conjunto com Skype for Business .

## <a name="prerequisites"></a>Pré-requisitos

Pré-requisitos para mover um usuário para o modo TeamsOnly:

- A organização deve ter o Azure AD Conexão configurado corretamente e estar sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configure Azure AD Conexão](configure-azure-ad-connect.md).
- Skype for Business híbrido deve ser configurado, conforme descrito em [Configure Skype for Business híbrido](configure-federation-with-skype-for-business-online.md).
- O usuário deve ter uma licença para Teams e Skype for Business Online (Plano 2). Mesmo após a aposentadoria do Skype for Business Online, a Skype for Business online ainda é necessária.  Além disso:
    - Se o usuário estiver habilitado para conferência discada no local, por padrão, o usuário também deve ter uma licença de Audioconferência atribuída Teams antes de mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para conferências de áudio na nuvem. Se, por alguma razão, você quiser mover um usuário para a nuvem, mas não usar a funcionalidade de audioconferência, poderá substituir essa seleção especificando o `BypassAudioConferencingCheck`parâmetro em`Move-CsUser`.
    - Se o usuário estiver habilitado para Enterprise Voice no local, por padrão, o usuário deve ter uma licença Sistema de Telefonia atribuída no Teams antes de mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para o sistema de telefonia na nuvem. Se, por algum motivo, você quiser mover um usuário para a nuvem, mas não usar Sistema de Telefonia funcionalidade, poderá substituir essa verificação especificando o `BypassEnterpriseVoiceCheck` parâmetro em `Move-CsUser` .


## <a name="moving-users"></a>Mover usuários

Quando um usuário é movido do local para a nuvem:

- Teams os usuários se tornam habilitados para interoperabilidade com Skype for Business usuários e, se eles são TeamsOnly, eles também podem federar com outras organizações.

- Os contatos do local são movidos para Teams.

- As reuniões existentes que organizaram que estão agendadas no futuro são migradas para online: se os usuários são movidos diretamente para o TeamsOnly (veja abaixo), as reuniões são convertidas em reuniões Teams, caso contrário, as reuniões permanecem Skype for Business mas serão migradas para que sejam hospedadas online em vez de locais.  A migração de reuniões ocorre de forma assíncrona e começa aproximadamente 90 minutos depois de mover o usuário.  Para determinar o status da migração de reunião, você pode usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Todo o conteúdo carregado antes da reunião não é movido.

Para mover os usuários para Teams, use o cmdlet Move-CsUser ou o painel de controle Skype for Business administrador, ambos são ferramentas locais. Essas ferramentas suportam os seguintes caminhos de movimentação:

- [Do Skype for Business Server (local)](move-users-from-on-premises-to-teams.md) diretamente para Teams Somente (que também os move para Skype for Business Online).  O comportamento para mover diretamente do local para o Teams Somente agora é automático, independentemente de qual versão do Skype for Business Server ou do Lync Server é usada. Não é mais necessário especificar a `-MoveToTeams` opção para obter esse comportamento.  
- [Do online (Teams somente ou não), para local](move-users-from-the-cloud-to-on-premises.md).

> [!NOTE] 
> Não é mais necessário especificar a opção -MoveToTeams no Move-CsUser para mover os usuários diretamente do local para o TeamsOnly. Anteriormente, se essa opção não foi especificada, os usuários mudaram de Skype for Business Server local para o Skype for Business Online, e seu modo permaneceu inalterado. Agora, ao mover um usuário do local para a nuvem com Move-CsUser, os usuários são atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local são automaticamente convertidas em reuniões de Teams, como se a opção tivesse sido especificada, independentemente de a opção ter sido `-MoveToTeams` realmente especificada. 
> 

## <a name="required-administrative-credentials"></a>Credenciais administrativas necessárias

Para mover os usuários entre o local e a nuvem, você deve usar uma conta com privilégios suficientes no ambiente de Skype for Business Server local, bem como na organização Teams local. Você pode usar uma conta que tenha todos os privilégios necessários ou pode usar duas contas, nesse caso, você acessaria as ferramentas locais usando credenciais locais e, nessas ferramentas, forneceria credenciais adicionais para uma conta administrativa Teams.  

- No ambiente local, o usuário que executa a movimentação deve ter as funções CSServerAdministrator e CsUserAdministrator em Skype for Business Server.
- No Teams, o usuário que executa a movimentação deve atender a um dos seguintes critérios:
  - O usuário é membro da função Administrador Global.
  - O usuário é membro das funções administrador Teams administrador e administrador do usuário.
  - O usuário é membro das funções administrador Skype for Business administrador e administrador do usuário.  

    > [!Important]
    > - Se você estiver usando o painel de controle de Skype for Business administrador, será solicitado a fornecer credenciais para uma conta Microsoft 365 com as funções apropriadas, conforme mencionado acima. Você deve fornecer uma conta que termine em .onmicrosoft.com. Se isso não for possível, use o cmdlet Move-CsUser.
    >- Se você estiver usando o Move-CsUser no PowerShell, poderá usar uma conta que termine em .onmicrosoft.com ou poderá usar qualquer conta local sincronizada no Azure AD, desde que você também especifique o parâmetro HostedMigrationOverrideUrl no cmdlet. O valor da URL de substituição de migração hospedada é uma variante da seguinte URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Na URL acima, substitua o XX por dois ou três caracteres, determinados da seguinte forma:
    >   - Em uma Teams do PowerShell, execute o seguinte cmdlet:<br>`Get-CsTenant|ft identity`
    >   - O valor resultante estará no seguinte formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - O código de dois ou três dígitos é o XX contido na seção, DC=lyncXX001. Se for um código de dois caracteres, será um dígito seguido por um número (como 0a). Se for um código de três caracteres, serão duas letras seguidas por um dígito (como jp1). Em todos os casos, você verá 001 imediatamente após o código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuração de voz

Se os usuários estão configurados para o Enterprise Voice no local, você precisará coordenar a atualização de sua configuração de voz ao movê-los para online ou, como alternativa, você pode migrá-los sem recursos de telefonia. As opções disponíveis dependem se o usuário estará usando o cliente Teams ou Skype for Business quando ele está online:

- Você pode atualizar o provedor de telefonia de um usuário para usar um [Plano de Chamada da Microsoft.](/microsoftteams/calling-plans-for-office-365) Essa é uma opção se os usuários usarão Teams ou Skype for Business clientes.
- Você pode continuar a usar seu provedor PSTN local:
  - Os usuários de voz que usarão Teams devem ser configurados para [Roteamento Direto.](/microsoftteams/direct-routing-plan) O Roteamento Direto só estará disponível depois que o usuário for movido do local para o online.
  - Os usuários de voz que usarão o cliente Skype for Business depois de serem movidos online devem ser configurados para a funcionalidade Skype for Business Híbrido Voice.

Para obter mais detalhes sobre opções de telefonia em ambientes híbridos, bem como uma matriz de suporte, consulte Contas de usuário em um ambiente híbrido com [conectividade PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Outras considerações

As políticas (por exemplo, para controlar mensagens, reuniões e comportamento de chamadas) em ambientes online e locais são independentes. Talvez você queira considerar a configuração de quaisquer políticas no ambiente e atribuí-las ao usuário antes de mover esse usuário do local para a nuvem, para que ele tenha a configuração correta assim que eles são migrados para online.

## <a name="see-also"></a>Confira também

[Migrar usuários de um ambiente local para o Teams](move-users-from-on-premises-to-teams.md)

[Configurando o Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planejar o Roteamento Direto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
