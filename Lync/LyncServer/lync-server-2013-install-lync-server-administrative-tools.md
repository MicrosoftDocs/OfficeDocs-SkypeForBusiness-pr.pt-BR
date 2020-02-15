---
title: 'Lync Server 2013: instalar ferramentas administrativas do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a0772244cf2158251b6a75a5b85b1adad86429
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Instalar ferramentas administrativas do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Este tópico descreve como instalar as ferramentas administrativas que você precisa usar para implantar e gerenciar o Lync Server 2013. As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Lync Server 2013. Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados. É altamente recomendável que você instale as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que a implantação do Lync Server 2013 que você está criando porque fazendo isso, verifique se as etapas de preparação dos serviços de domínio do Active Directory já estão concluído, permitindo que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia.

Certifique-se de revisar os requisitos de direitos de infra-estrutura, sistema operacional, software e administrador antes de instalar ou usar as ferramentas administrativas do Lync Server 2013. Para obter detalhes sobre os requisitos de infraestrutura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obter detalhes sobre os requisitos de sistema operacional e software para instalar as ferramentas administrativas do Lync Server 2013, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [suporte e requisitos adicionais do servidor no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Para obter detalhes sobre os direitos e permissões de usuário necessários para instalar e usar as ferramentas, consulte [direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Se a sua organização requer a localização de Serviços de Informações da Internet (IIS) e de todos os serviços web em uma unidade diferente da unidade do sistema, você pode alterar o caminho do local de instalação para os arquivos do Lync Server na caixa de diálogo de instalação. Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Para instalar as ferramentas administrativas do Lync Server 2013

1.  Faça logon como um administrador local (requisito mínimo) no computador onde você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão no sistema operacional Windows Vista ou Windows 7 e o UAC (Controle da Conta de Usuário) estiver habilitado, será solicitado para informar o nome de usuário e a senha do administrador local ou de um domínio equivalente.

2.  Localize a mídia de instalação no computador e clique duas vezes em \\Setup\\AMD64\\. exe.

3.  Se você receber uma solicitação para instalar o Microsoft Visual C++ 2008 distribuível, clique em **Sim**.

4.  Na página **local de instalação do Microsoft Lync Server 2013** , clique em **OK**. Altere este caminho para outro local ou unidade se precisa dos arquivos instalados em outra localização.
    
    <div>
    

    > [!IMPORTANT]  
    > Se sua organização exigir que você localize os serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo configuração. Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 será implantado também nessa unidade.

    
    </div>

5.  Na página **Acordo de licença do usuário final**, revise os termos de licença, clique em **Eu aceito** e em **OK**. Esta etapa é obrigatória antes de continuar.

6.  Na página **Microsoft Lync Server 2013 – assistente de implantação** , clique em **instalar ferramentas do administrador**.

7.  Quando a instalação for concluída com êxito, clique em **Sair**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Abrir as ferramentas administrativas do Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Ferramentas administrativas do Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

