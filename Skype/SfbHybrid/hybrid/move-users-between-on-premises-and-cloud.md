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
description: 'Resumo: em uma implantação local do Skype for Business Server habilitada para híbrido, você pode mover usuários entre o ambiente local e a nuvem (seja para o Microsoft Teams ou para o Skype for Business Online)..'
ms.openlocfilehash: b4b354a6a43ab58740a053f86d9b7da1faaeb0da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110667"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover os usuários entre um ambiente local e a nuvem

Em uma implantação local do Skype for Business Server habilitada para híbrido, é possível mover os usuários entre o ambiente local e a nuvem (para o Microsoft Teams ou para o Skype for Business Online). Se um usuário está localizado no local ou na nuvem, é conhecido como a página inicial do Skype for Business do usuário:

- Os usuários que estão no local interagem com servidores locais do Skype for Business.
- Os usuários que estão hospedados online podem interagir com o serviço do Skype for Business Online.

*Os usuários do Teams inerentemente têm uma casa do Skype for Business, quer usem o Skype for Business ou não.* Se você tiver usuários locais do Skype for Business que também estão usando o Teams (lado a lado), esses usuários ficam no local. Os usuários do Teams com o Skype for Business no local não têm a capacidade de interoperar com usuários do Skype for Business de seu cliente do Teams, nem podem se comunicar do Teams com usuários em uma organização federada. Essa funcionalidade só estará disponível depois que o usuário for movido do Skype for Business local para o online. Ao mover um usuário para o online, você pode permitir que ele use o Skype for Business Online (e, opcionalmente, o Teams) ou pode deixá-los Somente Teams. Se sua organização já estiver usando o Teams, é altamente recomendado que você a mova para o modo Somente Teams, o que garantirá que o roteamento de todas as chamadas e chats cheguem ao seu cliente do Teams. Para obter mais detalhes, consulte [a coexistência](/microsoftteams/coexistence-chat-calls-presence) do Teams com o Skype for Business e as diretrizes de migração e interoperabilidade para organizações que usam o Teams juntamente [com o Skype for Business.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>Pré-requisitos

Pré-requisitos para mover um usuário para a nuvem (seja para o modo Somente Skype for Business ou Somente Equipes):

- A organização deve ter o Azure AD Connect configurado corretamente e estar sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configure Azure AD Connect](configure-azure-ad-connect.md).
- O Skype for Business híbrido deve ser configurado, conforme descrito em [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
- O usuário deve receber uma licença do Skype for Business Online (Plano 2) e se for usar o Teams, será necessário ter uma licença dele também.  Além disso:
    - Se o usuário estiver habilitado para conferência discada no local, por padrão, o usuário também deve ter uma licença de Audioconferência atribuída no Microsoft 365 ou office 365 antes de executar a movimentação do usuário online. Depois de migrar para a nuvem, o usuário será provisionado para conferências de áudio na nuvem. Se, por algum motivo, você quiser mover um usuário para a nuvem, mas não usar a funcionalidade de audioconferência, poderá substituir essa verificação especificando o `BypassAudioConferencingCheck` parâmetro em `Move-CsUser` .
    - Se o usuário estiver habilitado para Enterprise Voice no local, por padrão, o usuário deve ter uma licença do Sistema de Telefonia atribuída no Microsoft 365 ou no Office 365 antes de mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para o sistema de telefonia na nuvem. Se, por algum motivo, você quiser mover um usuário para a nuvem, mas não usar a funcionalidade do Sistema de Telefonia, poderá substituir essa verificação especificando o `BypassEnterpriseVoiceCheck` parâmetro em `Move-CsUser` .


## <a name="moving-users"></a>Mover usuários

Quando um usuário é movido do local para a nuvem:

- O usuário começa a usar os serviços do Skype for Business Online na nuvem para qualquer funcionalidade do Skype for Business.
- Os usuários do Teams se tornam habilitados para a interoperabilidade com os usuários do Skype for Business e também podem federar-se com outras organizações.
- Os contatos do local são movidos para a nuvem (Skype for Business ou Teams).
- As reuniões existentes que organizaram que estão agendadas no futuro são migradas para online: se os usuários são movidos diretamente para o TeamsOnly (veja abaixo), as reuniões são convertidas em reuniões do Teams, caso contrário, as reuniões permanecem skype for Business, mas serão migradas para que sejam hospedadas online em vez de locais.  A migração de reuniões ocorre de forma assíncrona e começa aproximadamente 90 minutos depois de mover o usuário.  Para determinar o status da migração de reunião, você pode usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Todo o conteúdo carregado antes da reunião não é movido.

Para mover os usuários entre o local e a nuvem (seja para o Teams ou para o Skype for Business Online), use o cmdlet Move-CsUser ou o Painel de Controle de Administração do Skype for Business, ambos são ferramentas locais. Essas ferramentas oferecem suporte a três caminhos de mudança:

- [Do Skype for Business Server (local) ao Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Do Skype for Business Server (local) diretamente](move-users-from-on-premises-to-teams.md) para o Teams Only (que também os move para o Skype for Business Online).  A opção de mover diretamente do local para o Teams Only está disponível no Skype for Business Server 2019, bem como na Atualização Cumulativa 8 do Skype for Business Server 2015. As organizações que usam versões anteriores do Skype for Business Server podem mover os usuários para o Teams Only movendo-os primeiro para o Skype for Business Online e, em seguida, aplicando o modo Teams Only a esses usuários quando estiverem online.
- [Do online (se o Teams Somente ou não), para o local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciais administrativas necessárias

Para mover os usuários entre o local e a nuvem, você deve usar uma conta com privilégios suficientes no ambiente local do Skype for Business Server, bem como na organização do Microsoft 365 ou Office 365. Você pode usar uma conta que tenha todos os privilégios necessários ou usar duas contas, nesse caso, você acessaria as ferramentas locais usando credenciais locais e, nessas ferramentas, forneceria credenciais adicionais para uma conta administrativa do Microsoft 365 ou do Office 365.  

- No ambiente local, o usuário que realizará a mudança deve ter a função CSServerAdminstrator no Skype for Business Server.
- No Microsoft 365 e no Office 365, o usuário que está executando a movimentação deve ser um Administrador Global ou ter funções de Administrador do Skype for Business e Administrador do Usuário.  

    > [!Important]
    > - Se você estiver usando o Painel de Controle de Administração do Skype for Business, será solicitado a fornecer credenciais para uma conta do Microsoft 365 ou office 365 com as funções apropriadas, conforme mencionado acima. Você deve fornecer uma conta que termine em .onmicrosoft.com. Se isso não for possível, use o cmdlet Move-CsUser.
    >- Se você estiver usando o Move-CsUser no PowerShell, poderá usar uma conta que termine em .onmicrosoft.com ou poderá usar qualquer conta local sincronizada no Azure AD, desde que você também especifique o parâmetro HostedMigrationOverrideUrl no cmdlet. O valor da URL de substituição de migração hospedada é uma variante da seguinte URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Na URL acima, substitua o XX por dois ou três caracteres, determinados da seguinte forma:
    >   - Em uma sessão do PowerShell do Skype for Business Online, execute o seguinte cmdlet:<br>`Get-CsTenant|ft identity`
    >    - O valor resultante estará no seguinte formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - O código de dois ou três dígitos é o XX contido na seção, DC=lyncXX001. Se for um código de dois caracteres, será um dígito seguido por um número (como 0a). Se for um código de três caracteres, serão duas letras seguidas por um dígito (como jp1). Em todos os casos, você verá 001 imediatamente após o código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuração de voz

Se os usuários estão configurados para o Enterprise Voice no local, você precisará coordenar a atualização de sua configuração de voz ao movê-los para online ou, como alternativa, você pode migrá-los sem recursos de telefonia. As opções disponíveis dependem se o usuário estará usando o cliente do Teams ou do Skype for Business quando ele está online:

- Você pode atualizar o provedor de telefonia de um usuário para usar um [Plano de Chamada da Microsoft.](/microsoftteams/calling-plans-for-office-365) Essa é uma opção se os usuários usarão clientes do Teams ou do Skype for Business.
- Você pode continuar a usar seu provedor PSTN local:
  - Os usuários de voz que usarão o Teams devem estar configurados para [Roteamento Direto.](/microsoftteams/direct-routing-plan) O Roteamento Direto só estará disponível depois que o usuário for movido do local para o online.
  - Os usuários de voz que usarão o cliente skype for Business depois que eles são movidos online devem ser configurados para a funcionalidade de Voz Híbrida do Skype for Business.

Para obter mais detalhes sobre opções de telefonia em ambientes híbridos, bem como uma matriz de suporte, consulte Contas de usuário em um ambiente híbrido com [conectividade PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Outras considerações

As políticas (por exemplo, para controlar mensagens, reuniões e comportamento de chamadas) em ambientes online e locais são independentes. Talvez você queira considerar a configuração de quaisquer políticas no ambiente e atribuí-las ao usuário antes de mover esse usuário do local para a nuvem, para que ele tenha a configuração correta assim que eles são migrados para online.

## <a name="see-also"></a>Confira também

[Mover usuários do ambiente local para o Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Migrar usuários de um ambiente local para o Teams](move-users-from-on-premises-to-teams.md)

[Configurando o Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planejar o Roteamento Direto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)