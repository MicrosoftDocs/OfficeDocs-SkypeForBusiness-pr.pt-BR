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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: em uma implantação local do Skype for Business Server que está habilitada para o híbrido, você pode mover os usuários entre o ambiente local e a nuvem (seja no Microsoft Teams ou no Skype for Business online)..'
ms.openlocfilehash: eede6062bd9d03a2d9d6062a6dacb861ce37e14c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221121"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover os usuários entre um ambiente local e a nuvem

Em uma implantação local do Skype for Business Server habilitada para híbrido, é possível mover os usuários entre o ambiente local e a nuvem (para o Microsoft Teams ou para o Skype for Business Online). Se um usuário está localizado no local ou na nuvem, é conhecido como a página inicial do Skype for Business do usuário:

- Os usuários hospedados no local interagem com os servidores do Skype for Business local.
- Os usuários que estão hospedados online podem interagir com o serviço do Skype for Business Online.

*Os usuários do teams inerentemente à casa do Skype for Business, estejam usando o Skype for Business ou não.* Se você tiver usuários do Skype for Business no local que também usam o Microsoft Teams (lado a lado), esses usuários estão hospedados no local. Os usuários do Microsoft Teams com o Skype for Business no local não têm a capacidade de interoperar com os usuários do Skype for Business do seu cliente do Microsoft Teams, nem podem se comunicar de equipes com usuários em uma organização federada. Essa funcionalidade só estará disponível depois que o usuário for movido do Skype for Business no local para o online. Ao mover um usuário para o online, você pode permitir que ele use o Skype for Business Online (e, opcionalmente, o Teams) ou pode deixá-los Somente Teams. Se sua organização já estiver usando o Teams, é altamente recomendado que você a mova para o modo Somente Teams, o que garantirá que o roteamento de todas as chamadas e chats cheguem ao seu cliente do Teams. Para obter mais detalhes, consulte [Teams coexistência com Skype for Business](/microsoftteams/coexistence-chat-calls-presence) e [migração e orientação de interoperabilidade para organizações que usam o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Pré-requisitos

Pré-requisitos para mover um usuário para a nuvem (seja o Skype for Business somente ou o modo apenas do Microsoft Teams):

- A organização deve ter o Azure AD Connect configurado corretamente e sincronizar todos os atributos relevantes para o usuário, conforme descrito em [Configure Azure ad Connect](configure-azure-ad-connect.md).
- O Skype for Business híbrido deve ser configurado, conforme descrito em [Configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).
- O usuário deve receber uma licença do Skype for Business Online (Plano 2) e se for usar o Teams, será necessário ter uma licença dele também.  Além disso:
    - Se o usuário estiver habilitado para conferência discada no local, por padrão, o usuário também deverá ter uma licença de conferência de áudio atribuída no Microsoft 365 ou no Office 365 antes de executar mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para conferências de áudio na nuvem. Se, por algum motivo, você quiser mover um usuário para a nuvem, mas não usar a funcionalidade de audioconferência, poderá substituir essa verificação especificando o `BypassAudioConferencingCheck` parâmetro no `Move-CsUser` .
    - Se o usuário estiver habilitado para o Enterprise Voice no local, por padrão, o usuário deverá ter uma licença de sistema de telefonia atribuída no Microsoft 365 ou no Office 365 antes de você mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para o sistema de telefonia na nuvem. Se, por algum motivo, você quiser mover um usuário para a nuvem, mas não usar a funcionalidade do sistema de telefonia, poderá substituir essa verificação especificando o `BypassEnterpriseVoiceCheck` parâmetro no `Move-CsUser` .


## <a name="moving-users"></a>Mover usuários

Quando um usuário é movido do local para a nuvem:

- O usuário começa a usar os serviços do Skype for Business Online na nuvem para qualquer funcionalidade do Skype for Business.
- Os usuários do Teams se tornam habilitados para a interoperabilidade com os usuários do Skype for Business e também podem federar-se com outras organizações.
- Os contatos de no local são movidos para a nuvem (Skype for Business ou o Teams).
- Reuniões existentes organizadas por eles agendadas no futuro são migradas para online: se os usuários forem movidos diretamente para o TeamsOnly (veja abaixo), as reuniões serão convertidas em reuniões do Teams, caso contrário, as reuniões permanecerão com o Skype for Business, mas serão migradas para que sejam hospedadas online em vez de locais.  A migração de reuniões ocorre de forma assíncrona e começa aproximadamente 90 minutos depois de mover o usuário.  Para determinar o status da migração de reunião, você pode usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Todo o conteúdo carregado antes da reunião não é movido.

Para mover os usuários entre o local e a nuvem (seja o Microsoft Teams ou o Skype for Business online), use o cmdlet Move-CsUser ou o painel de controle de administração do Skype for Business, ambos são ferramentas locais. Essas ferramentas oferecem suporte a três caminhos de mudança:

- [Do Skype for Business Server (local) para o Skype for Business online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Do Skype for Business Server (local) diretamente para o Microsoft Teams](move-users-from-on-premises-to-teams.md) (que também os move para o Skype for Business online).  A opção de mover diretamente do local para o Microsoft Teams está disponível no Skype for Business Server 2019, bem como na atualização cumulativa 8 para o Skype for Business Server 2015. As organizações que usam versões anteriores do Skype for Business Server podem mover os usuários para o Teams Only movendo-os primeiro para o Skype for Business Online e, em seguida, aplicando o modo Teams Only a esses usuários quando estiverem online.
- [De online (seja apenas para equipes ou não), para o local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciais administrativas necessárias

Para mover os usuários entre o local e a nuvem, você deve usar uma conta com privilégios suficientes no ambiente do Skype for Business Server local, bem como na organização do Microsoft 365 ou do Office 365. Você pode usar uma conta que tenha todos os privilégios necessários ou usar duas contas, caso em que você acessará as ferramentas locais usando credenciais locais e, em seguida, nas ferramentas que fornecerá credenciais adicionais para uma conta administrativa do Microsoft 365 ou do Office 365.  

- No ambiente local, o usuário que realizará a mudança deve ter a função CSServerAdminstrator no Skype for Business Server.
- No Microsoft 365 e no Office 365, o usuário que está realizando a movimentação deve ser um administrador global ou ter as funções de administrador do Skype for Business e administrador de usuários.  

    > [!Important]
    > - Se estiver usando o painel de controle de administração do Skype for Business, você será solicitado a fornecer credenciais para uma conta do Microsoft 365 ou do Office 365 com as funções apropriadas, conforme indicado acima. Você deve fornecer uma conta que termina em. onmicrosoft.com. Se isso não for possível, use o cmdlet Move-CsUser.
    >- Se estiver usando o move-CsUser no PowerShell, você pode usar uma conta que termina em. onmicrosoft.com ou pode usar qualquer conta local que seja sincronizada com o Azure AD, desde que você também especifique o parâmetro HostedMigrationOverrideUrl no cmdlet. O valor da URL de substituição de migração hospedada é uma variante da seguinte URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Na URL acima, substitua o XX por dois ou três caracteres, determinado como a seguir:
    >   - Em uma sessão do PowerShell do Skype for Business Online, execute o seguinte cmdlet:<br>`Get-CsTenant|ft identity`
    >    - O valor resultante será no seguinte formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - O código de dois ou três dígitos é o XX contido na seção, DC = lyncXX001. Se for um código de dois caracteres, ele será um dígito seguido por um número (como 0A). Se for um código de três caracteres, será duas letras seguidas por um dígito (como JP1). Em todos os casos, você verá 001 imediatamente após o código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuração de voz

Se os usuários estiverem configurados para o Enterprise Voice no local, você precisará coordenar a atualização de sua configuração de voz ao movê-los para o modo online ou, como alternativa, pode migrá-los sem recursos de telefonia. As opções disponíveis dependem de o usuário usar o Microsoft Teams ou o cliente Skype for Business quando estiverem online:

- Você pode atualizar o provedor de telefonia de um usuário para usar um [plano de chamadas da Microsoft](/microsoftteams/calling-plans-for-office-365). Essa é uma opção se os usuários usarão o Teams ou clientes do Skype for Business.
- Você pode continuar a usar seu provedor PSTN local:
  - Os usuários de voz que usarão o Microsoft Teams devem ser configurados para [Roteamento direto](/microsoftteams/direct-routing-plan). O roteamento direto só estará disponível depois que o usuário for movido de local para online.
  - Os usuários de voz que usarão o cliente Skype for Business após serem movidos online devem ser configurados para a funcionalidade de voz híbrida do Skype for Business.

Para obter mais detalhes sobre as opções de telefonia em ambientes híbridos, bem como uma matriz de suporte, consulte [contas de usuário em um ambiente híbrido com conectividade PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Outras considerações

As políticas (por exemplo, para controlar mensagens, reuniões e comportamento de chamadas) em ambientes online e locais são independentes. Convém considerar a configuração de qualquer política no ambiente e atribuí-las ao usuário antes de mover o usuário do local para a nuvem, para que eles tenham a configuração correta assim que forem migrados para o online.

## <a name="see-also"></a>Confira também

[Mover usuários do ambiente local para o Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Migrar usuários de um ambiente local para o Teams](move-users-from-on-premises-to-teams.md)

[Configurando o Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planejar o Roteamento Direto](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
