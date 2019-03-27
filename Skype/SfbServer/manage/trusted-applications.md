---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que confia Skype para Business Server.
ms.openlocfilehash: 3ca8621148a4b6ce3530f23a61312f63f3d3cd30
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882139"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gerenciar aplicativos confiáveis no Skype para Business Server

Um *aplicativo confiável* é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que confia Skype para Business Server. Para obter detalhes sobre aplicativos UCMA, consulte "Unified Communications Managed API 3.0 Core documentação do SDK" em http://go.microsoft.com/fwlink/p/?linkId=210320.

Para publicar com êxito, habilitar ou desabilitar uma topologia quando a adição ou remoção de uma função de servidor, você deve estar conectado como um usuário que seja membro dos grupos RTCUniversalServerAdmins e administradores de domínio. 

Use este artigo para saber como configurar um novo servidor de aplicativos confiáveis, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar um novo servidor de aplicativos confiáveis

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique **Skype para o construtor de topologia de servidor de negócios**.

3.  Selecione **Baixar topologia da implantação existente**e clique em **Okey**.

4.  Na caixa de diálogo **Salvar topologia como** , clique no arquivo do construtor de topologia que você deseja usar e clique em **Salvar**.

5.  No painel esquerdo, clique com o botão **servidores de aplicativos confiáveis**e, em seguida, clique em **Novo Pool de aplicativos confiáveis**.

6.  Insira o **FQDN do Pool** do pool de aplicativos confiáveis, selecione se ele será um servidor único ou vários servidores e clique em **Avançar**.

7.  Na página **Selecionar o próximo salto** , na lista, selecione o Skype para pool de Front End do servidor de negócios.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Skype para Business Server**e, em seguida, no menu **ações** , clique em **Publicar topologia**.
    
    O **Pool de aplicativos confiáveis** deve ter foi criado com êxito e associado ao pool de Front-End correto.


## <a name="view-a-list-of-trusted-applications"></a>Exibir uma lista de aplicativos confiáveis

Você pode usar o Skype para painel de controle do Business Server para exibir uma lista dos aplicativos confiáveis que você tiver implantado na sua Skype para ambiente de servidor de negócios. Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que confia Skype para Business Server. Essa relação de confiança está resumida na lista a seguir:

  - Aplicativos confiáveis não são desafiados para autenticação pelo Skype para Business Server.

  - Aplicativos confiáveis não são acelerados pelo Skype para Business Server para transações SIP, conexões ou voz de saída chamadas de protocolo da Internet (VoIP).

  - Aplicativos confiáveis podem representar qualquer usuário e participem de conferências sem aparecer em escalações.

  - Aplicativos confiáveis são altamente disponíveis e flexíveis.

No Skype para painel de controle do Business Server, você pode ver o nome dos aplicativos, o pool onde são executados e a porta que usam.


### <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  Usando uma conta de usuário atribuída à função do CsServerAdministrator, CsAdministrator, CsHelpDesk, ou CsViewOnlyAdministrator, faça logon em qualquer computador de sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype para Business Server, consulte [o controle de acesso baseado em função (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3.  Na barra de navegação à esquerda, clique em **topologia**e, em seguida, clique em **Aplicativos confiáveis**.

4.  Na página **Aplicativos confiáveis** , clique em um título de coluna para classificar os aplicativos, se necessário.


## <a name="view-trusted-application-information"></a>Exibir informações de aplicativos confiáveis

Você pode exibir informações sobre seus aplicativos confiáveis usando o Windows PowerShell e o cmdlet **Get-CsTrustedApplication** . Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicativos confiáveis

Para exibir todos os aplicativos confiáveis, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsConferenceDisclaimer
    
   Esse comando retorna informações semelhantes às seguintes para cada aplicativo confiável:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   Para obter detalhes, consulte [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
