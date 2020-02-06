---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Um aplicativo confiável é um aplicativo baseado em SDK do Microsoft Unified Communications Managed (UCMA) 3,0 Core API que é confiável para o Skype for Business Server.
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817072"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gerenciar aplicativos confiáveis no Skype for Business Server

Um *aplicativo confiável* é um aplicativo baseado em SDK do Microsoft Unified Communications Managed (UCMA) 3,0 Core API que é confiável para o Skype for Business Server. Para obter detalhes sobre aplicativos do UCMA, consulte "documentação do SDK do 3,0 Core Communications http://go.microsoft.com/fwlink/p/?linkId=210320Managed API" em.

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio. 

Use este artigo para saber como configurar um novo servidor de aplicativos confiável, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar um novo servidor de aplicativos confiável

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server**e em **Construtor de topologias do Skype for Business Server**.

3.  Selecione **baixar topologia da implantação existente**e, em seguida, clique em **OK**.

4.  Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologias que você deseja usar e, em seguida, clique em **salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e, em seguida, clique em **novo pool de aplicativos confiável**.

6.  Digite o **FQDN do pool** do pool de aplicativos confiáveis, selecione se ele será um único servidor ou vários servidores e clique em **Avançar**.

7.  Na lista **selecionar o próximo salto** , selecione o pool de front-end do Skype for Business Server.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Skype for Business Server**e, em seguida, no menu **ações** , clique em **publicar topologia**.
    
    O **pool de aplicativos confiável** deve ter sido criado com êxito e associado ao pool de front-end correto.


## <a name="view-a-list-of-trusted-applications"></a>Exibir uma lista de aplicativos confiáveis

Você pode usar o painel de controle do Skype for Business Server para exibir uma lista dos aplicativos confiáveis que você implantou em seu ambiente do Skype for Business Server. Um aplicativo confiável é um aplicativo baseado em SDK do Microsoft Unified Communications Managed (UCMA) 3,0 Core API que é confiável para o Skype for Business Server. Essa relação de confiança é resumida na seguinte lista:

  - Aplicativos confiáveis não são desafiados para autenticação pelo Skype for Business Server.

  - Os aplicativos confiáveis não são restringidos pelo Skype for Business Server para transações de SIP, conexões ou chamadas de protocolo de voz por Internet (VoIP) de saída.

  - Aplicativos confiáveis podem representar qualquer usuário e podem participar de conferências sem que apareçam em escalas.

  - Aplicativos confiáveis são altamente disponíveis e resilientes.

No painel de controle do Skype for Business Server, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles usam.


### <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  Usando uma conta de usuário atribuída à função do CsServerAdministrator, CsAdministrator, CsHelpDesk, ou CsViewOnlyAdministrator, faça logon em qualquer computador de sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype for Business Server, consulte [controle de acesso baseado em função (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3.  Na barra de navegação à esquerda, clique em **topologia**e, em seguida, clique em **aplicativo confiável**.

4.  Na página **aplicativo confiável** , clique em um título de coluna para classificar os aplicativos, se necessário.


## <a name="view-trusted-application-information"></a>Exibir informações de aplicativo confiável

Você pode exibir informações sobre seus aplicativos confiáveis usando o Windows PowerShell e o cmdlet **Get-CsTrustedApplication** . Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para exibir aplicativos confiáveis

Para ver todos os seus aplicativos confiáveis, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
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
