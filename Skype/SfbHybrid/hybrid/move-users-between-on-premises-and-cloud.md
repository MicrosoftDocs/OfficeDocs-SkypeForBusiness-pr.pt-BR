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
description: 'Resumo: em uma implantação local do Skype for Business Server que está habilitada para híbrido, você pode mover os usuários entre o ambiente local e a nuvem.'
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65303999"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover os usuários entre um ambiente local e a nuvem

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Em uma implantação local do Skype for Business Server que está habilitada para híbrido, você pode mover os usuários entre o ambiente local e o Teams. Se um usuário está localizado no local ou na nuvem, é conhecido como a página inicial do Skype for Business do usuário:

- Os usuários hospedados localmente interagem com servidores Skype for Business locais.
- Os usuários hospedados online podem interagir com o Teams serviço.

*Teams usuários inerentemente têm uma Skype for Business, independentemente de usarem Skype for Business ou não.* Se você tiver usuários locais Skype for Business que também estão usando Teams (lado a lado), esses usuários serão hospedados no local. Teams usuários com o Skype for Business local não podem interoperar com usuários do Skype for Business de seu cliente Teams, nem podem se comunicar do Teams com usuários em uma organização federada. Essa funcionalidade só estará totalmente disponível depois que o usuário for movido de Skype for Business local para online e tornar o TeamsOnly. É recomendável que você mova seus usuários para o modo TeamsOnly, o que garantirá que o roteamento de todos os chats e chamadas de entrada cheguem ao Teams cliente. Para obter mais informações, [Teams coexistência](/microsoftteams/coexistence-chat-calls-presence) com o Skype for Business e as diretrizes de [migração e interoperabilidade](/microsoftteams/migration-interop-guidance-for-teams-with-skype) para organizações que usam Teams em conjunto com Skype for Business.

## <a name="prerequisites"></a>Pré-requisitos

Pré-requisitos para mover um usuário para o modo TeamsOnly:

- A organização deve ter Azure AD Conexão configurado corretamente e estar sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configurar Azure AD Conexão](configure-azure-ad-connect.md).
- Skype for Business híbrido deve ser configurado, conforme descrito em [Configurar Skype for Business híbrido](configure-federation-with-skype-for-business-online.md).
- O usuário deve receber uma licença para Teams e Skype for Business Online (Plano 2). Mesmo após a desativação do Skype for Business Online, a Skype for Business Online ainda é necessária.  Além disso:
    - Se o usuário estiver habilitado para conferência discada no local, o usuário também deverá ter uma licença de Audioconferência atribuída no Teams antes de você mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para conferências de áudio na nuvem. 
    - Se o usuário estiver habilitado para Enterprise Voice local, o usuário deverá ter uma licença de Sistema de Telefonia atribuída no Teams antes de você mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para Sistema de Telefonia na nuvem. 


## <a name="moving-users"></a>Mover usuários

Quando um usuário é movido do local para a nuvem:

- Teams usuários são habilitados para interoperabilidade com Skype for Business usuários e, se forem TeamsOnly, também poderão federar com outras organizações.

- Os contatos do local são movidos para Teams.

- As reuniões existentes que eles organizaram agendadas no futuro são convertidas em Teams reuniões. A migração de reuniões ocorre de forma assíncrona e começa aproximadamente 90 minutos depois de mover o usuário.  Para determinar o status da migração de reunião, você pode usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Qualquer conteúdo carregado antes da reunião não é movido.

Para mover usuários para Teams, use o cmdlet Move-CsUser ou o Painel de Controle administrador do Skype for Business, ambos são ferramentas locais. Essas ferramentas dão suporte aos seguintes caminhos de movimentação:

- [De Skype for Business Server (local) diretamente para Teams somente](move-users-from-on-premises-to-teams.md).  O comportamento para mover-se diretamente do local para o Teams somente agora é automático, independentemente de qual versão do Skype for Business Server ou do Lync Server é usada. Não é mais necessário especificar a opção `-MoveToTeams` para obter esse comportamento.  
- [De online (Teams somente ou não) para o local](move-users-from-the-cloud-to-on-premises.md).

> [!NOTE] 
> Não é mais necessário especificar a opção -MoveToTeams no Move-CsUser para mover os usuários diretamente do local para o TeamsOnly. Anteriormente, se essa opção não fosse especificada, os usuários iam de ser hospedados no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado. Agora, ao mover um usuário do local para a nuvem com Move-CsUser, os usuários são atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local são convertidas automaticamente em reuniões de Teams, `-MoveToTeams` como se a opção tivesse sido especificada, independentemente de a opção ter sido realmente especificada. 
> 

## <a name="required-administrative-credentials"></a>Credenciais administrativas necessárias

Para mover os usuários entre o local e a nuvem, você deve usar uma conta com privilégios suficientes no ambiente de Skype for Business Server local e na Teams organização. Você pode usar uma conta que tenha todos os privilégios necessários ou pode usar duas contas. Se você usar duas contas, acessará as ferramentas locais usando credenciais locais e, nessas ferramentas, fornecerá credenciais adicionais para uma Teams administrativa.  

- No ambiente local, o usuário que executa a movimentação deve ter as funções CSServerAdministrator, CsUserAdministrator e RTCUniversalUserAdmins no Skype for Business Server.
- Nesse Teams, o usuário que está executando a movimentação deve ser membro de pelo menos uma das seguintes funções:
  - Função de Administrador Global
  - Teams de administrador
  - Skype for Business de administrador.  

    > [!Important]
    > - Se você estiver usando o Skype for Business administrador do Painel de Controle, será solicitado que você forneça credenciais para uma conta Microsoft 365 com as funções apropriadas, conforme mencionado acima. Você deve fornecer uma conta que termine em .onmicrosoft.com. Se isso não for possível, use o Move-CsUser cmdlet.
    >- Se você estiver usando o Move-CsUser no PowerShell, poderá usar uma conta que termina em .onmicrosoft.com ou usar qualquer conta local sincronizada com o Azure AD, desde que você também especifique o parâmetro HostedMigrationOverrideUrl no cmdlet. O valor da URL de substituição de migração hospedada é uma variante da seguinte URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Na URL acima, substitua o XX por dois ou três caracteres, determinados da seguinte maneira:
    >   - Em uma Teams do PowerShell, execute o seguinte cmdlet:<br>`Get-CsTenant | ft ServiceInstance`
    >   - O valor resultante estará no seguinte formato:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - O código de dois ou três caracteres é o XX contido na seção YYYY-XX-ZZ. Se for um código de dois caracteres, ele será um dígito seguido por um número (como 4A). Se for um código de três caracteres, serão duas letras seguidas por um dígito (como JP1). Um exemplo é NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Requisitos de configuração de voz

Se os usuários forem configurados para o Enterprise Voice no local, você precisará coordenar a atualização da configuração de voz ao movê-los para online. Como alternativa, você pode migrá-los sem recursos de telefonia. As opções disponíveis dependem se o usuário usará o Teams ou Skype for Business cliente quando estiver online:

- Você pode atualizar o provedor de telefonia de um usuário para usar um [Plano de Chamada da Microsoft](/microsoftteams/calling-plans-for-office-365). Essa é uma opção se os usuários usarão Teams ou Skype for Business clientes.
- Você pode continuar a usar seu provedor PSTN local:
  - Os usuários de voz que usarão Teams devem ser configurados para [Roteamento Direto](/microsoftteams/direct-routing-plan). O Roteamento Direto só estará disponível depois que o usuário for movido do local para o online.
  - Os usuários de voz que usarão o Skype for Business cliente após serem movidos online devem ser configurados para Skype for Business Híbrido voice.

Para obter mais informações sobre opções de telefonia em ambientes híbridos, incluindo uma matriz de suporte, consulte Contas de usuário em um ambiente híbrido com conectividade [PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Outras considerações

As políticas (por exemplo, para controlar mensagens, reuniões e comportamento de chamadas) em ambientes online e locais são independentes. Talvez você queira considerar a configuração de todas as políticas no ambiente e atribuí-las ao usuário antes de mover esse usuário do local para a nuvem, para que ele tenha a configuração correta assim que ele for migrado para online.

## <a name="see-also"></a>Confira também

[Migrar usuários de um ambiente local para o Teams](move-users-from-on-premises-to-teams.md)

[Configurando o Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planejar o Roteamento Direto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
