---
title: 'Lync Server 2013: Gerenciando a qualidade do serviço (QoS)'
ms.reviewer: ''
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f25d35f0d96c9e1681c6b4d2c2c3b3079aad34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Gerenciando a qualidade do serviço (QoS) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

A QoS (qualidade de serviço) é uma tecnologia de rede usada em algumas organizações para ajudar a oferecer uma experiência ideal para o usuário final para comunicações de áudio e vídeo. A QoS é mais comumente usada em redes em que a largura de banda é limitada: com um grande número de pacotes de rede competindo por uma quantidade relativamente pequena de largura de banda disponível, a qualidade do serviço fornece uma maneira para os administradores atribuirem prioridades maiores aos pacotes transportar dados de áudio ou vídeo. Ao fornecer esses pacotes, é provável que as comunicações de áudio e vídeo sejam concluídas com mais rapidez e menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação na Web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".

<div>


> [!NOTE]  
> Como regra geral, a qualidade do serviço aplica-se somente a sessões de comunicação em sua rede interna. Ao implementar QoS, você configura seus servidores e roteadores para dar suporte à marcação de pacotes; no entanto, você configura esses dispositivos para dar suporte à marcação de pacotes de uma maneira específica. Você não pode supor que a qualidade do serviço será compatível na Internet ou em outras redes. Mesmo que o serviço de qualidade seja compatível com outras redes, não há garantia de que a QoS será configurada da mesma maneira que você configurou o serviço na sua rede.



</div>

O Microsoft Lync Server 2013 não requer qualidade de serviço; Se você não usa o QoS no momento, não há necessidade de instalar o serviço antes de instalar o Lync Server 2013. Se você tiver uma quantidade considerável de perda de pacotes na rede, a maneira recomendada de aliviar esse problema é adicionar mais largura de banda. Se não for possível adicionar mais largura de banda, talvez você queira implementar a qualidade do serviço em vez disso.

O Lync Server 2013 oferece suporte completo para a qualidade do serviço: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Lync Server à sua infraestrutura de rede existente. Para fazer isso, você deve executar as seguintes tarefas:

  - [Habilitando a QoS no Lync Server 2013 para dispositivos que não são baseados no Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS é desativada em computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar o Lync Server para habilitar e desabilitar a qualidade do serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos DSCP usados por esses dispositivos.

  - [Configurar intervalos de porta no Lync Server 2013 para servidores de conferência, aplicativo e mediação](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Com o Lync Server 2013, você não habilita ou desabilita a qualidade do serviço por, digamos, definir um valor de propriedade como verdadeiro ou falso. Em vez disso, habilite a qualidade de serviço Configurando intervalos de porta e, em seguida, criando e aplicando a política de grupo. Se, mais tarde, você decidir não usar o QoS, poderá "Desabilitar" a qualidade do serviço simplesmente removendo os objetos de política de grupo apropriados.

  - [Configurando intervalos de porta para seus servidores de borda no Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores.

  - [Configurar intervalos de porta para seus clientes do Microsoft Lync no Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Esses intervalos de porta se aplicam apenas aos computadores cliente e são tipicamente diferentes dos intervalos de porta configurados em seus servidores.

  - [Configurar uma política de qualidade de serviço no Lync Server 2013 para servidores de conferência, aplicativo e mediação](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Essas políticas determinam os códigos DSCP aplicados a diferentes tipos de pacote.

  - [Configurar uma política de qualidade de serviço para seus servidores de borda a/V no Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Isso deve ser executado somente para o lado interno de seus servidores de borda. Isso porque a qualidade do serviço foi projetada para ser usada em sua rede interna e não na Internet.

  - [Configuração de políticas de qualidade de serviço no Lync Server 2013 para clientes em execução no Windows 7 ou no Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Observe que o Microsoft Lync Server 2013 não é compatível com QoS para outros sistemas operacionais Windows, como Windows Vista ou Windows XP.

  - Configurando a [qualidade do serviço em dispositivos Microsoft Lync Phone Edition no Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Por padrão, a QoS está habilitada para dispositivos do Lync Phone Edition. No entanto, talvez você queira alterar o valor padrão de DSCP para garantir que todos os pacotes de áudio em sua organização usem o mesmo código DSCP.

<div>


> [!NOTE]  
> Se você estiver usando o Microsoft Windows Server 2012 ou o Windows Server 2012 R2, talvez esteja interessado no novo conjunto de cmdlets do Windows PowerShell disponíveis para o gerenciamento da qualidade do serviço nessa plataforma. Para obter mais informações, consulte cmdlets de qualidade de serviço de rede no [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)Windows PowerShell em.



</div>

</div>

<span> </span>

</div>

</div>

</div>

