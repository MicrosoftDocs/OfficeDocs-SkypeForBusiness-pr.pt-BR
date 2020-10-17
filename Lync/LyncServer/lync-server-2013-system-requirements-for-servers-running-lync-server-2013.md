---
title: 'Lync Server 2013: requisitos de sistema para servidores que executam o Lync Server 2013'
description: 'Lync Server 2013: requisitos de sistema para servidores que executam o Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562647"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Requisitos do sistema para servidores que executam o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-07-24_

<div>


> [!NOTE]
> Para obter detalhes sobre os requisitos de hardware, consulte <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.



</div>

Os servidores Standard Edition e Enterprise Edition compartilham os mesmos requisitos de software.

Os servidores que executam o Lync Server 2013, Enterprise Edition são destinados a grandes organizações como a implantação organizacional principal. O servidor Enterprise Edition foi projetado para acomodar aproximadamente 80.000 usuários por pool. Os servidores que executam o Lync Server 2013, Standard Edition são destinados a organizações menores e locais remotos da implantação da organização principal. Um par de servidores Standard Edition pode suportar até 5.000 usuários.. Para obter detalhes sobre as diferenças entre servidores Standard Edition e servidores Enterprise Edition, consulte [Deployment Overview for Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Instalação do sistema operacional

<div>


> [!IMPORTANT]
> O Lync Server 2013 está disponível somente em uma edição de 64 bits, que requer hardware de 64 bits e uma edição de 64 bits do sistema operacional Windows Server. Uma edição de 32 bits do Lync Server 2013 não está disponível nesta versão.



</div>

O Standard Edition e o servidor Enterprise Edition podem usar qualquer um dos seguintes:

  - Windows Server 2008 R2 SP1 ou Service Pack mais recente

  - Windows Server 2012

  - Windows Server 2012 R2

Instale o software do sistema operacional no servidor Standard Edition ou no servidor front-end Enterprise Edition. Aplique todas as atualizações para deixar o sistema operacional com a atualização mais recente e a atualização necessária de nível consistente com os padrões da organização. Para obter mais detalhes sobre os requisitos de operação, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

> [!NOTE] 
> A atualização in-loco do sistema operacional não é suportada pelo Lync Server 2013.  Você deve implantar um pool separado e migrar os usuários para o novo pool com um sistema operacional diferente.

<div>


> [!NOTE]
> Para que o Lync Server 2013 funcione no Windows Server 2012 R2, talvez seja necessário alterar o valor de uma chave de registro no Windows Server. Essa alteração pode ser necessária para que os certificados funcionem corretamente e para que os clientes possam se registrar em aparelhos de filial persistente. Para obter mais informações, consulte <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Software adicional para o Lync Server 2013

Além das atualizações necessárias para o sistema operacional, o Lync Server 2013 requer funções de sistema operacional, recursos e software a operar. Para obter detalhes sobre o software adicional que deve ser instalado antes de publicar sua topologia e como instalar o Lync Server 2013, consulte [Additional Software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Software adicional necessário para todas as funções de servidor

Em todas as funções de servidor, você também deve verificar se a interface de linha de comando do Windows PowerShell 3,0 e o Microsoft .NET Framework 4,5 estão instalados.

Além disso, a interface de linha de comando 3,0 do Windows PowerShell e o Microsoft .NET Framework 4,5 são necessários em qualquer computador em que você executará as ferramentas administrativas do Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

O Lync Server 2013 requer que você instale o Windows PowerShell 3,0 em cada computador que fará parte da sua topologia do Lync Server. Para obter detalhes sobre como instalar o Windows PowerShell 3,0, consulte [instalando o Windows powershell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]
> No Windows Server &nbsp; 2008 &nbsp; R2 com SP1, a interface de linha de comando do Windows PowerShell 3,0 não pode ser instalada antes da instalação do Microsoft .net Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Ao instalar o Microsoft .NET Framework 4,5 em servidores que executarão o Lync Server 2013 no Windows Server 2012 ou Windows Server 2012 R2, você deve executar uma etapa adicional. Após a instalação do .NET Framework 4,5, use o Gerenciador do servidor para instalar a ativação HTTP.

**Para instalar a ativação HTTP do .NET 4,5 no Windows Server 2012 ou no Windows Server 2012 R2**

1.  No menu **Iniciar** , clique em **programas**, em **Ferramentas administrativas**e, em seguida, clique em **Gerenciador do servidor**.

2.  No Gerenciador de servidores, em **Resumo de recursos**, escolha **Adicionar recursos**.

3.  Expanda o **.NET Framework 4,5**.

4.  Selecione **ativação do WCF** , se ainda não estiver selecionada. Em seguida, selecione **ativação de http**.

5.  Clique em **Avançar** e siga as instruções para concluir a instalação.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

