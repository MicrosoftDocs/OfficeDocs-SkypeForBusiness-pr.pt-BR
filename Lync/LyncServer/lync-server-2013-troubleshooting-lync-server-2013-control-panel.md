---
title: 'Lync Server 2013: solução de problemas do painel de controle do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 629fa8ea52148e25bd37fa448d9762fbfd557788
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Resolver problemas do painel de controle do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-07-28_

Este tópico fornece informações e procedimentos que podem ajudá-lo a solucionar problemas de acesso ao Lync Server 2013 painel de controle.

<div>

## <a name="internet-browser-requirements"></a>Requisitos de navegador da Internet

O painel de controle do Lync Server exige que o plug-in do navegador Microsoft Silverlight versão 4.0.50524.0 ou versão mais recente esteja instalado. Se o Silverlight não estiver instalado ou se uma versão anterior estiver instalada, siga as instruções na mensagem para instalar a versão necessária.

<div>


> [!NOTE]  
> Outros requisitos de software para o painel de controle do Lync Server pertencem ao sistema operacional em que o painel de controle do Lync Server e todas as outras ferramentas administrativas do Lync Server 2013 podem ser instaladas. Para obter detalhes, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System support in Lync Server 2013</A> na documentação de suporte.



</div>

Se o seu navegador da Internet bloquear a instalação do Silverlight devido a considerações de segurança, adicione o Uniform Resource Locator (URL) que abre o painel de controle do Lync Server à lista de sites confiáveis. Nas configurações de segurança do Internet Explorer, certifique-se de **Executar controles e plug-ins do ActiveX** está definido para **Habilitado**. Para obter detalhes, [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060)consulte. Além disso, certifique-se de que o navegador está configurado para usar SSL 3.0.

Se o navegador da Internet estiver configurado para usar um servidor proxy, verifique se o navegador está configurado para ignorar o servidor proxy para os sites que são detectados automaticamente como sites internos. Ou adicione o endereço à lista de exceções do navegador nas definições de configuração de servidor proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Requisitos de registro DNS e de certificado para a URL de Acesso Administrativo

Se você configurou uma URL simples para acessar o painel de controle do Lync Server, certifique-se de que você também configurou o registro de recurso de host (A) do DNS (sistema de nomes de domínio) estático e o certificado necessário para usar essa URL de acesso administrativo. Se você alterar a URL base a qualquer momento, certifique-se de que a alteração é refletida no registro DNS apropriado e no certificado e que você executa o *Enable-CsComputer* em cada diretor e servidor front-end para registrar a alteração. Para obter detalhes, consulte os seguintes tópicos na documentação de Planejamento:

  - [Planejamento de URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Para obter os procedimentos passo a passo para configurar a URL de acesso administrativo, consulte [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos de IIS (Serviços de Informações da Internet)

O painel de controle do Lync Server é um dos componentes do Lync Server 2013 que requer o IIS (serviços de informações da Internet). Em particular, verifique se o redirecionamento de HTTP e os recursos de autenticação do Windows estão habilitados e se o W3SVC (Serviço de Publicação na World Wide Web ) está em execução.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dependência do Serviço de Publicação na World Wide Web (Serviço do Windows)

Quando o serviço de publicação na World Wide Web é interrompido, não é possível acessar o painel de controle do Lync Server. Você pode reiniciar o serviço usando o MMC (Console de Gerenciamento Microsoft) dos Serviços do Windows.

**Para iniciar o Serviço de Publicação na World Wide Web**

1.  Faça logon no computador em que o serviço de publicação na World Wide Web está instalado como parte do serviços de informações da Internet (IIS).

2.  Clique em **Iniciar**, em **Ferramentas administrativas** e em **Serviços**.

3.  Com o botão direito do mouse em **Serviço de Publicação na World Wide Web**e clique em **Iniciar**.

</div>

<div>

## <a name="application-pool-mode"></a>Modo de pool de aplicativos

Configure o IIS para que o pool de aplicativos CsManagementAppPool use a conta do Serviço de Rede como sua identidade do modelo de processo.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Permissões e direitos de usuário

Você deve entrar no painel de controle do Lync Server usando uma conta de domínio que seja membro do grupo CsAdministrator ou usando uma conta à qual você tenha delegado direitos e permissões de usuário. Você não pode entrar no painel de controle do Lync Server usando uma conta de máquina local. Para obter detalhes sobre como delegar tarefas administrativas por meio de controle de acesso baseado em função (RBAC), consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.

Se você usar uma URL simples para acessar o painel de controle do Lync Server, verifique se os servidores Web foram adicionados aos grupos RTCUniversalServerAdmins e RTCUniversalUserAdmins.

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

