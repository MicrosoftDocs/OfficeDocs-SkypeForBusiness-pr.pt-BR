---
title: Mover usuários entre locais e em nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumo: Em uma implantação local do Skype para Business Server está habilitado para o híbrido, você pode mover usuários entre o ambiente local e a nuvem (entre Microsoft Teams ou Skype para Business Online)..'
ms.openlocfilehash: 492a2a7d14af77bc0b90afe03f0d36de0f830129
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247604"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover usuários entre locais e em nuvem

Em uma implantação local do Skype para Business Server está habilitado para o híbrido, você pode mover usuários entre o ambiente local e a nuvem (entre Microsoft Teams ou Skype para Business Online). Se um usuário está localizado no local ou na nuvem é conhecido como Skype do usuário para a página inicial de negócios:

- Os usuários hospedados no local interagem com Skype local para os servidores de negócios.
- Os usuários hospedados online podem interagir com Skype para serviço de Business Online.

*Usuários de equipes têm um Skype para casa de negócios, se eles usam Skype para negócios ou não.* Se você tiver Skype local para usuários corporativos também usando equipes (lado a lado), esses usuários hospedados no local. Usuários de equipes com Skype for Business no local não têm a capacidade de interoperar com Skype para usuários de negócios do cliente suas equipes, nem podem se comunicam de equipes com usuários em uma organização federada. Essa funcionalidade está disponível somente após o usuário é movido do Skype for Business no local para online. Quando você mover um usuário online, você pode permitir que eles usem Skype para Business Online (e, opcionalmente, equipes) ou você pode torná-los somente equipes. Se sua organização já está usando para equipes, é altamente recomendável que você mova para equipes somente modo, que garantirá que o roteamento de todas as chats de entrada e chamadas chega à cliente suas equipes. Para obter mais detalhes, consulte [coexistência de equipes com Skype para negócios](/microsoftteams/coexistence-chat-calls-presence) e [orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios e de migração](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Pré-requisitos

Pré-requisitos para mover um usuário para a nuvem (se Skype para o modo de negócios apenas ou equipes apenas):

- A organização deve ter o Azure Connect da AD configurado corretamente e ser sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configurar o Azure AD Connect](configure-azure-ad-connect.md).
- Skype para o híbrido de negócios deve ser configurado conforme descrito em [Configurar Skype para o híbrido de negócios](configure-federation-with-skype-for-business-online.md).
- O usuário deve ser atribuído uma licença para Skype para negócios Online (plano 2) e se eles usarão equipes, eles também devem ter uma licença de equipes.  Além disso:
    - Se o usuário está habilitado para conferência discada em localmente, por padrão, a que o usuário também deve ter uma licença de audioconferência atribuída no Office 365 antes de executar move o usuário online. Uma vez migrados para a nuvem, o usuário será provisionado para conferência de áudio na nuvem. Se por algum motivo que você deseja mover um usuário na nuvem, mas não usar a funcionalidade de conferência de áudio, você pode substituir essa verificação, especificando o `BypassAudioConferencingCheck` parâmetro em `Move-CsUser`.
    - Se o usuário está habilitado para o Enterprise Voice no local, por padrão o usuário deve ter uma licença de sistema telefônico atribuída no Office 365, antes de mover o usuário online. Uma vez Migrated para a nuvem, o usuário será provisionada para o sistema telefônico na nuvem. Se por algum motivo que você deseja mover um usuário na nuvem, mas não usar a funcionalidade de sistema telefônico, você pode substituir essa verificação, especificando o `BypassEnterpriseVoiceCheck`parâmetro em `Move-CsUser`.


## <a name="moving-users"></a>Migração de usuários

Quando um usuário é movido do local para a nuvem:

- O usuário inicia usando Skype para serviços corporativos Online na nuvem para qualquer Skype para a funcionalidade de negócios.
- Usuários de equipes ficado habilitados para a interoperabilidade com Skype para usuários empresariais e eles também podem criar uma federação com outras organizações.
- Contatos de no local são movidos para a nuvem seja (Skype for Business) ou equipes.
- Existentes reuniões organizados por eles agendados no futuro são migradas para online. Migração de reuniões acontece de forma assíncrona e começa a aproximadamente 90 minutos depois de mover o usuário.  Para determinar o status da migração da reunião, você pode usar o [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Observe que qualquer conteúdo que foi carregado antes de começar a reunião não é movido.

Para mover usuários no local e a nuvem (entre equipes ou Skype para Business Online), use o cmdlet Move-CsUser ou o Skype para painel de controle de administração de negócios, ambos os quais são as ferramentas de local. Essas ferramentas suportam três caminhos de movimentação diferentes:

- [Do Skype para Business Server (no local) para Skype para negócios Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Do Skype para Business Server (no local) diretamente para as equipes somente](move-users-from-on-premises-to-teams.md) (que também são movidos para Skype para Business Online).  A opção para passar diretamente do local para equipes só está disponível em Skype para Business Server 2019, bem como 8 de atualização cumulativa para Skype para Business Server 2015. As organizações que usam versões anteriores do Skype para Business Server podem mover usuários para equipes somente primeiro movê-las para Skype para Business Online e, em seguida, aplicando o modo TeamsOnly a esses usuários quando estiverem online.
- [Do online (se Teams somente ou não), como no local](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenciais administrativas necessárias

Para mover usuários no local e na nuvem, você deve usar uma conta com privilégios suficientes em ambos o Skype local para ambiente de servidor de negócios, bem como inquilino do Office 365. Você pode usar uma conta que tenha todos os privilégios necessários, ou você pode usar as duas contas, caso em que você acesse as ferramentas de local usando credenciais locais e, em seguida, nessas ferramentas seria fornecer credenciais adicionais para um Office 365 conta administrativa.  

- No ambiente local, o usuário que está executando a movimentação deve ter a função de CSServerAdminstrator no Skype para Business Server.
- No Office 365, o usuário que está executando a movimentação deve ser um Administrador Global ou deve ter as duas Skype para funções de administrador de negócios e de usuário administrador.  

    > [!Important]
    > - Se você estiver usando o Skype para painel de controle de administração de negócios, você deverá fornecer credenciais para uma conta do Office 365 com as funções apropriadas, conforme indicado acima. Você deve fornecer uma conta que termina em. onmicrosoft.com. Se não for possível, em seguida, use o cmdlet Move-CsUser.
    >- Se você estiver usando o Move-CsUser no PowerShell, você pode usar uma conta que termina em. onmicrosoft.com, ou você pode usar qualquer conta local sincronizado no Azure AD, desde que você especificar também o parâmetro HostedMigrationOverrideUrl no cmdlet . O valor da URL de substituição de migração hospedado é um variant da seguinte URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Na URL acima, substitua o XX com dois ou três caracteres, determinados da seguinte maneira:
    >   - Em um Skype para sessão de negócios Online PowerShell, execute o seguinte cmdlet:<br>`Get-CsTenant|ft identity`
    >    - O valor resultante será no seguinte formato:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - O código de dois ou três dígitos é o XX contido na seção, DC = lyncXX001. Se for um código de dois caracteres, ele será um dígito seguido por um número (por exemplo, 0a). Se for um código de três caracteres, ele será duas letras seguidas por um dígito (por exemplo, jp1). Em todos os casos, você verá 001 imediatamente após o código XX.


## <a name="voice-configuration-requirements"></a>Requisitos de configuração de voz

Se os usuários estiverem configurados para enterprise voice no local, você precisará coordenar atualizar sua configuração de voz ao movê-los para online, ou, Alternativamente, você poderia migrá-los sem os recursos de telefonia. As opções disponíveis dependem se o usuário estará usando as equipes ou Skype para o cliente de negócios quando estiverem online:

- Você pode atualizar o provedor de telefonia de um usuário para usar um [Plano do Microsoft chamar](/microsoftteams/calling-plans-for-office-365). Essa é uma opção, se os usuários usarão equipes ou Skype para clientes corporativos.
- Você pode continuar a usar seu provedor PSTN local:
  - Usuários de voz que usarão as equipes devem ser configurados para [Roteamento direto](/microsoftteams/direct-routing-plan). Roteamento direto está disponível somente após o usuário é movido de no local para online.
  - Usuários de voz que usarão o Skype para o cliente de negócios depois que eles forem movidos online devem ser configurados para Skype para a funcionalidade de negócios híbrida voz.

Para obter mais detalhes sobre as opções de telefonia em ambientes híbridos, bem como uma matriz de suporte, consulte [contas de usuário em um ambiente híbrido com conectividade PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Outras considerações

As diretivas (como para controlar mensagens, reuniões e chamar o comportamento) no local e online ambientes são independentes. Convém considerar Configurando quaisquer políticas no ambiente e atribuindo-los ao usuário antes de passar que o usuário do local para a nuvem, para que eles tenham a configuração correta, assim que eles são migrados para online.

## <a name="see-also"></a>Consulte também

[Mover usuários do local para o Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Mover os usuários no local para equipes](move-users-from-on-premises-to-teams.md)

[Configurando o Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planejar o Roteamento Direto](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)