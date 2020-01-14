---
title: 'Lync Server 2013: Requisitos de sistema para servidores executando Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301cd234e2218fc806423a9ffe9beb49994402f2
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104490"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Requisitos de sistema para servidores executando Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-07-24_

<div>


> [!NOTE]  
> Para obter detalhes sobre os requisitos de hardware, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor para o Lync Server 2013</A>.



</div>

Os servidores Standard Edition e Enterprise Edition compartilham os mesmos requisitos de software.

Os servidores que executam o Lync Server 2013, Enterprise Edition são destinados a grandes organizações como a principal implantação organizacional. O Enterprise Edition Server foi projetado para dimensionar para cerca de 80.000 usuários hospedados por pool. Os servidores que executam o Lync Server 2013, Standard Edition são destinados a organizações menores e locais remotos da implantação da organização principal. Um par de servidores de edição padrão pode oferecer suporte a até 5.000 usuários... Para obter detalhes sobre as diferenças entre os servidores de edição padrão e os servidores Enterprise Edition, consulte [visão geral de implantação do Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Instalação do sistema operacional

<div>


> [!IMPORTANT]  
> O Lync Server 2013 está disponível apenas em uma edição de 64 bits, que exige hardware de 64 bits e uma edição de 64 bits do sistema operacional Windows Server. Uma edição de 32 bits do Lync Server 2013 não está disponível nesta versão.



</div>

O Standard Edition e o Enterprise Edition Server podem usar qualquer um dos seguintes:

  - Windows Server 2008 R2 SP1 ou Service Pack mais recente

  - Windows Server 2012

  - Windows Server 2012 R2

Instale o software do sistema operacional no servidor Standard Edition ou no servidor front-end da Enterprise Edition. Aplique todas as atualizações para que o sistema operacional vá para a atualização mais recente e o nível de atualização necessário consistente com os padrões da sua organização. Para obter mais detalhes sobre os requisitos operacionais, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

> [!NOTE] A atualização in-loco do sistema operacional não é compatível com o Lync Server 2013.  Você deve implantar um pool separado e migrar usuários para o novo pool com um sistema operacional diferente.

<div>


> [!NOTE]  
> Para o Lync Server 2013 funcionar no Windows Server 2012 R2, talvez seja necessário alterar o valor de uma chave do registro no Windows Server. Essa alteração pode ser necessária para que os certificados funcionem corretamente e para que os clientes se inscrevam em aparelhos de ramificação sobreviventes. Para saber mais, confira <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Software adicional para o Lync Server 2013

Além das atualizações necessárias para o sistema operacional, o Lync Server 2013 requer funções do sistema operacional, recursos e software para funcionar. Para obter detalhes sobre o software adicional que deve ser instalado antes de publicar sua topologia e instalar o Lync Server 2013, consulte [requisitos adicionais de software para o Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Software adicional necessário para todas as funções de servidor

Em todas as funções de servidor, você também deve verificar se a interface de linha de comando do Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 estão instaladas.

Além disso, a interface de linha de comando do Windows PowerShell 3,0 e o Microsoft .NET Framework 4,5 são necessárias em qualquer computador em que você executar as ferramentas administrativas do Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

O Lync Server 2013 exige a instalação do Windows PowerShell 3,0 em cada computador que fará parte da sua topologia do Lync Server. Para obter detalhes sobre como instalar o Windows PowerShell 3,0, consulte [instalando o Windows powershell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]  
> No Windows Server&nbsp;2008&nbsp;R2 com SP1, a interface de linha de comando do Windows PowerShell 3,0 não pode ser instalada antes de instalar o Microsoft .NET Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft.NET Framework 4.5

Ao instalar o Microsoft .NET Framework 4,5 em servidores que executarão o Lync Server 2013 no Windows Server 2012 ou Windows Server 2012 R2, você deve executar uma etapa adicional. Após instalar o .NET Framework 4,5, use o Gerenciador de servidores para instalar a ativação HTTP.

**Para instalar a ativação HTTP do .NET 4,5 no Windows Server 2012 ou no Windows Server 2012 R2**

1.  No menu **Iniciar** , clique em **programas**e, em seguida, clique em **Ferramentas administrativas**e, em seguida, clique em **Gerenciador de servidores**.

2.  No Gerenciador de servidores, em **Resumo de recursos**, escolha **Adicionar recursos**.

3.  Expanda o **.NET Framework 4,5**.

4.  Selecione **ativação do WCF** , se ainda não estiver selecionado. Em seguida, selecione **ativação http**.

5.  Clique em **Avançar** e siga as instruções para concluir a instalação.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

