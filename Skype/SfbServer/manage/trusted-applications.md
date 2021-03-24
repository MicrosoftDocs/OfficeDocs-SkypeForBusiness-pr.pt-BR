---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server.
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103157"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gerenciar aplicativos confiáveis no Skype for Business Server

Um *aplicativo confiável* é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server. Para obter detalhes sobre aplicativos UCMA, consulte "Unified Communications Managed API 3.0 Core SDK Documentation" em https://go.microsoft.com/fwlink/p/?linkId=210320 .

Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio. 

Use este artigo para saber como configurar um novo servidor de aplicativos confiáveis, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar um novo servidor de aplicativo confiável

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Iniciar Construtor de Topologias: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business Server** e em Construtor de Topologias do Skype for Business **Server.**

3.  Selecione **Baixar topologia da implantação existente** e clique em **OK**.

4.  Na caixa **de diálogo Salvar Topologia Como,** clique no arquivo Construtor de Topologias que você deseja usar e clique em **Salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **Servidores de aplicativos confiáveis** e clique em **Novo Pool de Aplicativos Confiáveis.**

6.  Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.

7.  Na página **Selecionar o próximo salto,** na lista, selecione o pool de Front-End do Skype for Business Server.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Skype for Business Server** e, no menu **Ações,** clique em **Publicar Topologia**.
    
    O **Pool de Aplicativos Confiáveis** deve ter sido criado com êxito e associado ao pool de Front-End correto.


## <a name="view-a-list-of-trusted-applications"></a>Exibir uma lista de aplicativos confiáveis

Você pode usar o Painel de Controle do Skype for Business Server para exibir uma lista dos aplicativos confiáveis que você implantou em seu ambiente do Skype for Business Server. Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server. Essa relação de confiança é resumida na lista a seguir:

  - Aplicativos confiáveis não são desafiados para autenticação pelo Skype for Business Server.

  - Os aplicativos confiáveis não são aceleradas pelo Skype for Business Server para transações SIP, conexões ou chamadas voIP (Voice over Internet Protocol) de saída.

  - Aplicativos confiáveis podem representar qualquer usuário e participar de conferências sem aparecer em lista.

  - Os aplicativos confiáveis são altamente disponíveis e resilientes.

No Painel de Controle do Skype for Business Server, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles usam.


### <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  Em uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinida disponíveis no Skype for Business Server, consulte Controle de acesso baseado em função [(RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.

3.  Na barra de navegação esquerda, clique em **Topologia** e clique em **Aplicativo Confiável.**

4.  Na página **Aplicativo Confiável,** clique em um título de coluna para classificar os aplicativos, se necessário.


## <a name="view-trusted-application-information"></a>Exibir informações de aplicativos confiáveis

Você pode exibir informações sobre seus aplicativos confiáveis usando Windows PowerShell e o cmdlet **Get-CsTrustedApplication.** Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicativos confiáveis

Para exibir todos os seus aplicativos confiáveis, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
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
    
   Para detalhes, consulte [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).