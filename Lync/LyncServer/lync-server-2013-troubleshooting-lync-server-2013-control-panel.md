---
title: 'Lync Server 2013: solução de problemas do painel de controle do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Solução de problemas do painel de controle do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-07-28_

Este tópico fornece informações e procedimentos que podem ajudá-lo a solucionar problemas de acesso ao painel de controle do Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Requisitos de navegador da Internet

O painel de controle do Lync Server requer a instalação do plug-in do navegador Microsoft Silverlight 4.0.50524.0 ou versão mais recente. Se o Silverlight não estiver instalado ou se uma versão anterior estiver instalada, siga as instruções na mensagem para instalar a versão necessária.

<div>


> [!NOTE]  
> Outros requisitos de software para o painel de controle do Lync Server pertencem ao sistema operacional em que o painel de controle do Lync Server e todas as outras ferramentas administrativas do Lync Server 2013 podem ser instaladas. Para obter detalhes, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013</A> na documentação de suporte.



</div>

Se o seu navegador da Internet bloquear a instalação do Silverlight devido a considerações de segurança, adicione o Uniform Resource Locator (URL) que abre o painel de controle do Lync Server à lista de sites confiáveis. Nas configurações de segurança do Internet Explorer, certifique-se de que a **execução de controles ActiveX e plug-ins** esteja definida como **Enabled**. Para obter detalhes, [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)consulte. Além disso, verifique se o navegador está configurado para usar SSL 3,0.

Se o navegador da Internet estiver configurado para usar um servidor proxy, verifique se o navegador está configurado para ignorar o servidor proxy para sites que sejam detectados automaticamente como sites internos. Ou adicione o endereço à lista de exceções do navegador nas definições de configuração do servidor proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Requisitos de registro e certificado DNS para a URL de acesso administrativo

Se você configurou uma URL simples para acessar o painel de controle do Lync Server, verifique também se configurou o registro de recurso host (A) do sistema de nome de domínio estático (A) e o certificado necessário para usar essa URL de acesso administrativo. Se você alterar a URL base a qualquer momento, certifique-se de que a alteração seja refletida no registro DNS e no certificado apropriados e execute o *Enable-CsComputer* em cada director e servidor front-end para registrar a alteração. Para obter detalhes, consulte os seguintes tópicos na documentação de planejamento:

  - [Planejamento de URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Para obter procedimentos passo a passo para configurar a URL de acesso administrativo, consulte [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos dos serviços de informações da Internet (IIS)

O painel de controle do Lync Server é um dos componentes do Lync Server 2013 que exige serviços de informações da Internet (IIS). Em particular, verifique se o redirecionamento de HTTP e os recursos de autenticação do Windows estão habilitados e se o W3SVC (World Wide Web Publishing Service) está em execução.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dependência do serviço de publicação na World Wide (serviço do Windows)

Quando o serviço de publicação na World Wide Web é interrompido, você não pode acessar o painel de controle do Lync Server. Você pode reiniciar o serviço usando o MMC (console de gerenciamento Microsoft) de serviços do Windows.

**Para iniciar o serviço de publicação na World Wide Web**

1.  Faça logon no computador em que o serviço de publicação na World Wide Web é instalado como parte do IIS (serviços de informações da Internet).

2.  Clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **Serviços**.

3.  Clique com o botão direito do mouse em **serviço de publicação na World Wide Web**e clique em **Iniciar**.

</div>

<div>

## <a name="application-pool-mode"></a>Modo de pool de aplicativos

Configure o IIS para que o pool de aplicativos do CsManagementAppPool use a conta de serviço de rede como identidade do modelo de processo.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Direitos e permissões de usuário

Você deve conectar-se ao painel de controle do Lync Server usando uma conta de domínio que seja membro do grupo CsAdministrator ou usando uma conta para a qual você tenha direitos e permissões de usuário delegado. Você não pode entrar no painel de controle do Lync Server usando uma conta de computador local. Para obter detalhes sobre como delegar tarefas administrativas por meio do controle de acesso baseado em função (RBAC), consulte [planejar o controle de acesso baseado em função no Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.

Se você usar uma URL simples para acessar o painel de controle do Lync Server, certifique-se de que os servidores Web sejam adicionados aos grupos RTCUniversalServerAdmins e RTCUniversalUserAdmins.

</div>

<div>

## <a name="see-also"></a>Confira também


[Ferramentas administrativas do Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

