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
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705870"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Mover os usuários entre um ambiente local e a nuvem

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Em uma implantação local do Skype for Business Server, os usuários do Skype for Business também podem usar o Teams, mas nem todas as funcionalidades do Teams estão disponíveis para esses usuários, desde que estejam configurados para usar a implantação Skype for Business Server local. Esses usuários são ditos como "hospedados" localmente e determinadas funcionalidades do Teams não estão disponíveis enquanto esses usuários estão hospedados localmente, por exemplo:
- Chamadas federadas e chats por meio do cliente do Teams do usuário com usuários em outras organizações não estão disponíveis
- Comunicação de interoperabilidade por meio do cliente do Teams do usuário com outros usuários na organização que usam Skype for Business cliente.
- Funcionalidade de chamada PSTN (se o usuário receber uma licença do Sistema de Telefonia).

Para obter a funcionalidade completa do Teams, esses usuários devem ser movidos do Skype for Business local para a nuvem, momento em que o usuário se torna TeamsOnly. O ato de mover um usuário do local para a nuvem definirá o modo de coexistência do usuário como TeamsOnly. Depois que os usuários são movidos para a nuvem, eles são TeamsOnly, o que significa que todos os chats e chamadas de entrada chegam ao cliente do Teams. Para obter mais informações, consulte [a coexistência do Teams](/microsoftteams/coexistence-chat-calls-presence) com Skype for Business e as diretrizes de migração e interoperabilidade para organizações que usam o [Teams junto com o Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Para mover usuários da implantação local Skype for Business Server para a nuvem, é necessário a configuração de Skype for Business [híbrido](/skypeforbusiness/hybrid/plan-hybrid-connectivity).  Depois que a implantação estiver habilitada para híbrido, você poderá mover os usuários do ambiente local para a nuvem para torná-los TeamsOnly, conforme descrito abaixo. Se necessário, você também pode mover os usuários do TeamsOnly de volta para a implantação local do Skype for Bsuiness. 



## <a name="prerequisites"></a>Pré-requisitos

Pré-requisitos para mover um usuário para o modo TeamsOnly:

- A organização deve ter Azure AD Conectar corretamente e estar sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configurar Azure AD Connect](configure-azure-ad-connect.md).
- Skype for Business híbrido deve ser configurado, conforme descrito em [Configurar Skype for Business híbrido](configure-federation-with-skype-for-business-online.md).
- O usuário deve receber uma licença do Teams e do Skype for Business Online (Plano 2). Mesmo após a desativação do Skype for Business Online, a licença do Skype for Business Online ainda é necessária.  Além disso:
    - Se o usuário estiver habilitado para conferência discada no local, o usuário também deverá ter uma licença de Audioconferência atribuída no Teams antes de você mover o usuário online. Depois de migrar para a nuvem, o usuário será provisionado para conferências de áudio na nuvem. 
    - Se o usuário estiver habilitado para Enterprise Voice local, o usuário deverá ter uma licença do Telefone do Teams atribuída no Teams antes de você mover o usuário online. Depois de migrado para a nuvem, o usuário será provisionado para o Sistema de Telefonia na nuvem. 
  
A partir de 31 de julho de 2022, para mover usuários entre uma implantação local e a nuvem, você deve usar a seguinte versão mínima do Skype for Business Server ou do Lync Server:

</br>
</br>

|Produto local|Versão mínima necessária|Build mínimo necessário|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 com Hotfix 7|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>Mover usuários

Quando um usuário é movido do local para a nuvem:

- O usuário se torna um usuário teamsOnly, o que significa que o usuário:
   -  Recebe e inicia todos os chats e chamadas no cliente do Teams.
   -  Agenda todas as reuniões no Teams.
   -  Não é possível iniciar chats ou chamadas ou agendar reuniões no Skype for Business.
   -  Pode ingressar Skype for Business reuniões que já têm ou recebem no futuro. No entanto, depois que a Microsoft remover a infraestrutura do Skype for Business Online para um determinado usuário do TeamsOnly, os usuários do TeamsOnly só poderão ingressar Skype for Business reuniões anonimamente. A partir de outubro de 2022, os usuários migrados do local para o Teams somente em organizações híbridas não serão mais provisionados com a infraestrutura Skype for Business Online. Se esses usuários forem convidados para uma reunião Skype for Business, eles precisarão ingressar anonimamente. Para obter detalhes, [consulte Diretrizes para organizações com implantações locais de Skype for Business Server](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server).

- Os usuários são habilitados para interoperabilidade com Skype for Business usuários e também podem federar com outras organizações.
- Os contatos do local são movidos para o Teams.
- As reuniões existentes que eles organizaram agendadas no futuro são convertidas em reuniões do Teams. A migração de reuniões ocorre de forma assíncrona e começa aproximadamente 90 minutos depois de mover o usuário.  Para determinar o status da migração de reunião, você pode usar [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Qualquer conteúdo carregado antes da reunião não é movido.
- Os usuários que recebem uma licença do Telefone do Teams podem acessar a funcionalidade PSTN depois de configurados corretamente.
 
Para mover usuários para o Teams, use o cmdlet Move-CsUser ou o Skype for Business Administração Painel de Controle, que são ferramentas locais. Essas ferramentas dão suporte aos seguintes caminhos de movimentação:

- [Do Skype for Business Server (local) somente para o Teams](move-users-from-on-premises-to-teams.md).
- [De online (somente teams ou não), até o local](move-users-from-the-cloud-to-on-premises.md).


> [!NOTE] 
>  O comportamento de migrar diretamente do local para o Teams é automático, independentemente de qual versão do Skype for Business Server ou do Lync Server é usada. Não é mais necessário especificar a `-MoveToTeams` opção de `Move-CsUser` mover os usuários diretamente do local para o TeamsOnly. Anteriormente, se essa opção não fosse especificada, os usuários iam de ser hospedados no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado. Agora, ao mover um usuário do local para a `Move-CsUser`nuvem com o modo TeamsOnly, os usuários são atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local são convertidas automaticamente em reuniões do Teams, `-MoveToTeams` assim como se a opção tivesse sido especificada, independentemente de a opção ter sido realmente especificada. 


## <a name="required-administrative-credentials"></a>Credenciais administrativas necessárias

Para mover usuários entre o local e a nuvem, você deve usar uma conta com privilégios suficientes no ambiente de Skype for Business Server local e na organização do Teams. Você pode usar uma conta que tenha todos os privilégios necessários ou pode usar duas contas. Se você usar duas contas, acessará as ferramentas locais usando credenciais locais e, nessas ferramentas, fornecerá credenciais adicionais para uma conta administrativa do Teams.  

- No ambiente local, o usuário que executa a movimentação deve ter as funções CSServerAdministrator, CsUserAdministrator e RTCUniversalUserAdmins no Skype for Business Server.
- No Teams, o usuário que executa a movimentação deve ser membro de pelo menos uma das seguintes funções:
  - Função de Administrador Global
  - Função de Administrador do Teams
  - Skype for Business de administrador.  

    > [!Important]
    > - Se você estiver usando o Skype for Business Administração Painel de Controle, será solicitado que você forneça credenciais para uma conta do Microsoft 365 com as funções apropriadas, conforme mencionado acima. Você deve fornecer uma conta que termine em .onmicrosoft.com. Se isso não for possível, use o Move-CsUser cmdlet.
    >- Se você estiver usando o Move-CsUser no PowerShell, poderá usar uma conta que termina em .onmicrosoft.com ou usar qualquer conta local sincronizada com o Azure AD, desde que você também especifique o parâmetro HostedMigrationOverrideUrl no cmdlet. O valor da URL de substituição de migração hospedada é uma variante da seguinte URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Na URL acima, substitua o XX por dois ou três caracteres, determinados da seguinte maneira:
    >   - Em uma sessão do PowerShell do Teams, execute o seguinte cmdlet:<br>`Get-CsTenant | ft ServiceInstance`
    >   - O valor resultante estará no seguinte formato:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - O código de dois ou três caracteres é o XX contido na seção YYYY-XX-ZZ. Se for um código de dois caracteres, ele será um dígito seguido por um número (como 4A). Se for um código de três caracteres, serão duas letras seguidas por um dígito (como JP1). Um exemplo é NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Requisitos de configuração

Se os usuários forem configurados para o Enterprise Voice no local, você precisará coordenar a atualização da configuração de voz ao movê-los para online. Como alternativa, você pode migrá-los sem recursos de telefonia. 
- Você pode atualizar o provedor de telefonia de um usuário para usar um [Plano de Chamada da Microsoft](/microsoftteams/calling-plans-for-office-365). Essa é uma opção se os usuários usarão o Teams ou Skype for Business clientes.
- Você pode continuar a usar seu provedor PSTN local:
  - Os usuários de voz que usarão o Teams devem ser configurados para o [Roteamento Direto](/microsoftteams/direct-routing-plan). O Roteamento Direto só estará disponível depois que o usuário for movido do local para o online.

Para obter mais informações sobre opções de telefonia em ambientes híbridos, incluindo uma matriz de suporte, consulte Contas de usuário em um ambiente híbrido com conectividade [PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Outras considerações

As políticas (por exemplo, para controlar mensagens, reuniões e comportamento de chamadas) em ambientes online e locais são independentes. Talvez você queira considerar a configuração de todas as políticas no ambiente e atribuí-las ao usuário antes de mover esse usuário do local para a nuvem, para que ele tenha a configuração correta assim que ele for migrado para online.

## <a name="see-also"></a>Confira também

[Migrar usuários de um ambiente local para o Teams](move-users-from-on-premises-to-teams.md)

[Configurando o Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planejar o Roteamento Direto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
