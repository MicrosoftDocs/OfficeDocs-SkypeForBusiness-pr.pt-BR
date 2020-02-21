---
title: 'Lync Server 2013: preparando e instalando o analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59bcaca40414c9bd99e451846c0339d0af6e7bf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Preparando e instalando o Best Practices Analyzer no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Você deve estar conectado como um membro do grupo Administradores para executar as tarefas que estão descritas neste tópico.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Os requisitos de sistema para a instalação do Analisador de Práticas Recomendadas

Para executar o Lync Server 2013, o analisador de práticas recomendadas para verificar seu ambiente, o computador deve estar executando uma edição de 64 bits de um dos seguintes sistemas operacionais:

  - Sistema operacional Windows Server 2008 R2 com Service Pack 1 (SP1) Standard

  - Sistema operacional Windows Server 2008 R2 com SP1 Enterprise

  - Sistema operacional Windows Server 2008 R2 com SP1 datacenter

  - Sistema operacional Windows Server 2012 datacenter

  - Sistema operacional Windows Server 2012 Standard

  - Sistema operacional Windows Server 2012 Enterprise

  - Sistema operacional Windows Server 2012 R2 Datacenter

  - Sistema operacional Windows Server 2012 R2 Standard

  - Sistema operacional Windows Server 2012 R2 Enterprise

  - Sistema operacional Windows 8

  - Sistema operacional Windows 7

O computador também deve estar executando o seguinte:

  - Microsoft .NET Framework 4.5. Para o Lync Server 2013, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013.

  - Lync Server 2013, componentes principais.

  - Pacote de compatibilidade com versões anteriores da WMI. Para obter detalhes, consulte [instalar o pacote de compatibilidade com versões anteriores do WMI](install-wmi-backward-compatibility-package.md) na documentação de migração.

  - Windows PowerShell 3.0. Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) na documentação de implantação.

Você pode instalar o Best Practices Analyzer em computadores com um sistema operacional compatível que não esteja executando o Lync Server 2013, componentes principais ou o pacote de compatibilidade com versões anteriores do WMI, mas você pode usar o analisador de práticas recomendadas nesses computadores apenas para exibir relatórios, não para executar verificações.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Escolhendo um computador para instalação

É recomendável instalar o Lync Server 2013, o Best Practices Analyzer em um computador dedicado ao gerenciamento do Lync Server 2013. Você pode instalar a ferramenta em um servidor executando o Lync Server 2013 ou um computador administrativo executando as ferramentas administrativas do Lync Server 2013. Se você instalar a ferramenta em um servidor que está executando o Lync Server, recomendamos usar a ferramenta para verificar apenas esse servidor.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Instalando o Analisador de Práticas Recomendadas

Você pode baixar o Best Practices Analyzer for Lync Server 2013 [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)em.

Para instalar o Analisador de Práticas Recomendadas, inicie o arquivo RtcBPA.msi do Arquivo Microsoft Installer (.msi) no computador no qual você deseja instalar a ferramenta e, em seguida, siga as instruções na tela. O local padrão para instalar os arquivos de programa \<é arquivos\>\\\\de programa da unidade de\\sistema do Lync Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

