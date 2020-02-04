---
title: 'Lync Server 2013: Instalar ferramentas administrativas do Lync Server'
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
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Instalar ferramentas administrativas do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Este tópico descreve como instalar as ferramentas administrativas que você precisa usar para implantar e gerenciar o Lync Server 2013. As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Lync Server 2013. Além disso, você pode instalar as ferramentas administrativas em outros computadores, como consoles administrativos dedicados. É altamente recomendável que você instale as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que a implantação do Lync Server 2013 que você está criando porque está fazendo isso, verifique se as etapas de preparação dos serviços de domínio Active Directory já estão concluído, que permite que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia.

Verifique se revisar os requisitos de infraestrutura, sistema operacional, software e administrador antes de instalar ou usar as ferramentas administrativas do Lync Server 2013. Para obter detalhes sobre requisitos de infraestrutura, consulte [requisitos de infraestrutura de ferramentas administrativas no Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obter detalhes sobre os requisitos do sistema operacional e do software para instalar as ferramentas administrativas do Lync Server 2013, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md), além [de requisitos e suporte de servidor adicionais no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Para obter detalhes sobre os direitos de usuário e as permissões necessárias para instalar e usar as ferramentas, consulte [direitos de administrador e permissões necessárias para a instalação e a administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

<div>


> [!IMPORTANT]  
> Se a sua organização exigir que você localize os serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar. Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Para instalar as ferramentas administrativas do Lync Server 2013

1.  Faça logon como administrador local (requisito mínimo) para o computador em que você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão nos sistemas operacionais Windows Vista ou Windows 7, e o controle de conta de usuário (UAC) estiver habilitado, você será solicitado a fornecer o administrador local ou um nome de usuário e uma senha equivalentes ao domínio.

2.  Localize a mídia de instalação no seu computador e, em seguida, \\clique\\duas\\vezes em setup AMD64 setup. exe.

3.  Se você for solicitado a instalar o Microsoft Visual C++ 2008 Redistributable, clique em **Sim**.

4.  Na página **local de instalação do Microsoft Lync Server 2013** , clique em **OK**. Altere esse caminho para outro local ou unidade se precisar ter os arquivos instalados em outro local.
    
    <div>
    

    > [!IMPORTANT]  
    > Se a sua organização exigir que você localize os serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo Configurar. Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Lync Server 2013 será implantado nesta unidade também.

    
    </div>

5.  Na página **contrato de licença de usuário final** , examine os termos de licença, clique em **aceito**e, em seguida, clique em **OK**. Esta etapa é necessária para que você possa continuar.

6.  Na página **Microsoft Lync Server 2013 – assistente de implantação** , clique em **instalar ferramentas de administrador**.

7.  Quando a instalação for concluída com êxito, clique em **sair**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Abrir ferramentas administrativas do Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Ferramentas administrativas do Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

