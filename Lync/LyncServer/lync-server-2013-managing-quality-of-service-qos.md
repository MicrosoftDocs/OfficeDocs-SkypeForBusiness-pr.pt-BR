---
title: 'Lync Server 2013: Gerenciando a qualidade de serviço (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
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
ms.openlocfilehash: b72fbd1275060ce01d56cb64e11cdd27f38b2e54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Gerenciando a qualidade de serviço (QoS) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

A Qualidade de Serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a fornecer a melhor experiência ao usuário final para comunicações de áudio e vídeo. a QoS é usada mais frequentemente em rede com largura de banda limitada: com uma grande número de pacotes de rede para uma quantidade relativamente pequena de largura de banda disponível, a Qualidade de Serviço fornece aos administradores uma maneira de atribuírem prioridades mais altas a pacotes que carregam dados de áudio e vídeo. Ao conceder uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo têm uma probabilidade maior de serem concluídas mais rápido e com menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação da Web ou backups de bancos de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".

<div>


> [!NOTE]  
> Como regra geral, a Qualidade de Serviço se aplica somente a sessões de comunicação em sua rede interna. Ao implementar a QoS, você configure seus servidores e roteadores para suportar a marcação de pacotes; no entanto, você configura esses dispositivos para suportar a marcação de pacotes de forma específica. Não é possível considerar que a Qualidade de Serviço será suportada na Internet ou em outras redes. Mesmo se a Qualidade de Serviço for suportada em outras redes, não há garantia de que a QoS será configurada de forma igual a que você configurou o serviço em sua rede.



</div>

O Microsoft Lync Server 2013 não requer qualidade de serviço; Se você não usa QoS no momento, não é necessário instalar o serviço antes de instalar o Lync Server 2013. Se você notar uma quantidade considerável de perda de pacotes em sua rede, a maneira recomendada de aliviar esse problema é adicionar mais largura de banda. Se não for possível adicionar mais largura de banda, então pode ser necessário implementar a Qualidade de Serviço.

O Lync Server 2013 oferece suporte completo para a qualidade de serviço: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Lync Server à sua infraestrutura de rede existente. Para fazer isso, você precisa executar as seguintes tarefas:

  - [Habilitando a QoS no Lync Server 2013 para dispositivos que não são baseados no Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS está desativada para computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar o Lync Server para habilitar e desabilitar a qualidade do serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos de DSCP usados por esses dispositivos.

  - [Configurando intervalos de portas no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Com o Lync Server 2013, não é possível habilitar ou desabilitar a qualidade de serviço, digamos, definir um valor de propriedade como true ou false. Em vez disso, você ativa a Qualidade de Serviço configurando intervalos de porta e, em seguida, criando e aplicando a Política de grupo. Se decidir posteriormente não usar a QoS, você pode “desativar” a Qualidade de Serviço removendo os objetos de Política de grupo apropriados.

  - [Configurando intervalos de portas para seus servidores de borda no Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores.

  - [Configurando intervalos de portas para seus clientes Microsoft Lync no Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Esses intervalos de porta se aplicam somente a computadores cliente e normalmente não são os mesmos que os intervalos de porta configurados em seus servidores.

  - [Configuração de uma política de qualidade de serviço no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Essas políticas determinam os códigos DSCP que são aplicados a tipos de pacotes diferentes.

  - [Configurando uma política de qualidade de serviço para seus servidores de borda a/V no Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Isso deve ser executado somente para o lado interno de seus servidores de borda. Isso ocorre pois a Qualidade do Serviço foi projetada para uso em sua rede interna e não na Internet.

  - [Configuração de políticas de qualidade de serviço no Lync Server 2013 para clientes que executam o Windows 7 ou Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Observe que o Microsoft Lync Server 2013 não oferece suporte a QoS para outros sistemas operacionais Windows, como o Windows Vista ou o Windows XP.

  - [Configurando a qualidade de serviço nos dispositivos do Microsoft Lync Phone Edition no Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Por padrão, a QoS é habilitada para dispositivos do Lync Phone Edition. No entanto, pode ser necessário alterar o valor padrão de DSCP para garantir que todos os pacotes de áudio em sua organização usem o mesmo código de DSCP.

<div>


> [!NOTE]  
> Se você estiver usando o Microsoft Windows Server 2012 ou o Windows Server 2012 R2, você pode estar interessado no novo conjunto de cmdlets do Windows PowerShell disponíveis para o gerenciamento da qualidade de serviço nessa plataforma. Para obter mais informações, consulte Network Quality of Service cmdlets in Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)em.



</div>

</div>

<span> </span>

</div>

</div>

</div>

