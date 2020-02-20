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
description: Um aplicativo confiável é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Skype for Business Server.
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151221"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gerenciar aplicativos confiáveis no Skype for Business Server

Um *aplicativo confiável* é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Skype for Business Server. Para obter detalhes sobre os aplicativos do UCMA, consulte "documentação do SDK básico do Unified https://go.microsoft.com/fwlink/p/?linkId=210320Communications Managed API 3,0 em.

Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio. 

Use este artigo para saber como configurar um novo servidor de aplicativos confiáveis, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar um novo servidor de aplicativos confiáveis

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server**e em **Construtor de topologias do Skype for Business Server**.

3.  Selecione **Baixar topologia da implantação existente** e clique em **OK**.

4.  Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologia que você deseja usar e clique em **salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e clique em **novo pool de aplicativos confiáveis**.

6.  Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.

7.  Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Skype for Business Server.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Skype for Business Server**e, no menu **ações** , clique em **publicar topologia**.
    
    O **pool de aplicativos confiáveis** deve ter sido criado com êxito e associado ao pool de front-ends correto.


## <a name="view-a-list-of-trusted-applications"></a>Exibir uma lista de aplicativos confiáveis

Você pode usar o painel de controle do Skype for Business Server para exibir uma lista dos aplicativos confiáveis que você implantou no seu ambiente do Skype for Business Server. Um aplicativo confiável é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Skype for Business Server. Essa relação de confiança é resumida na seguinte lista:

  - Os aplicativos confiáveis não são desafiados para autenticação pelo Skype for Business Server.

  - Os aplicativos confiáveis não são limitados pelo Skype for Business Server para transações SIP, conexões ou chamadas VoIP (Voice over Internet Protocol) de saída.

  - Aplicativos confiáveis podem representar qualquer usuário e podem participar de conferências sem que apareçam nas listas.

  - Os aplicativos confiáveis estão altamente disponíveis e resistentes.

No painel de controle do Skype for Business Server, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles utilizam.


### <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  A partir de uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype for Business Server, consulte [funções de controle de acesso baseado em função (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.

3.  Na barra de navegação esquerda, clique em **topologia**e, em seguida, clique em **aplicativo confiável**.

4.  Na página **aplicativo confiável** , clique em um cabeçalho de coluna para classificar os aplicativos, se necessário.


## <a name="view-trusted-application-information"></a>Exibir informações de aplicativo confiável

Você pode exibir informações sobre seus aplicativos confiáveis usando o Windows PowerShell e o cmdlet **Get-CsTrustedApplication** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicativos confiáveis

Para exibir todos os seus aplicativos confiáveis, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
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
    
   Para detalhes, consulte [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
