---
title: Configurando a qualidade do serviço em dispositivos Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="3903d-102">Configurando a qualidade do serviço em dispositivos Microsoft Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3903d-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3903d-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3903d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3903d-104">Embora a QoS (qualidade de serviço) não seja habilitada por padrão para dispositivos como iPhones, a QoS é habilitada por padrão para dispositivos que executam o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="3903d-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="3903d-105">(Esses dispositivos são comumente referidos como telefones de comunicação unificada ou UC.) Para verificar isso, execute o seguinte comando do Windows PowerShell no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="3903d-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="3903d-106">Se você não fez nenhuma alteração nas configurações de seu telefone UC, receberá as informações que se assemelharão a isto:</span><span class="sxs-lookup"><span data-stu-id="3903d-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="3903d-107">Para fins de qualidade de serviço, apenas uma dessas propriedades é de interesse: VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="3903d-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="3903d-108">O VoiceDiffServTag representa o valor de DSCP atribuído ao tráfego de voz que emana de um dispositivo Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="3903d-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="3903d-109">O parâmetro Voice8021p não é mais compatível com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3903d-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="3903d-110">O parâmetro ainda é válido para fins de compatibilidade com versões anteriores do Microsoft Lync Server 2010; no entanto, ele não tem efeito em dispositivos usados com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3903d-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="3903d-111">Na maioria das redes, a marcação de pacotes do Lync Phone Edition com um VoiceDiffServTag de 40 não deve causar problemas.</span><span class="sxs-lookup"><span data-stu-id="3903d-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="3903d-112">No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="3903d-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="3903d-113">Para manter a consistência em toda a sua rede, talvez você queira alterar a propriedade VoiceDiffServTag de seus telefones UC para o 46.</span><span class="sxs-lookup"><span data-stu-id="3903d-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="3903d-114">Para fazer isso, você pode usar o Windows PowerShell ou o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3903d-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="3903d-115">Para modificar o valor VoiceDiffServTag usando o Windows PowerShell, execute o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="3903d-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="3903d-116">O comando anterior modifica o conjunto global de configurações de configuração de telefone de comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="3903d-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="3903d-117">No entanto, observe que as configurações de telefone UC também podem ser atribuídas ao escopo do site.</span><span class="sxs-lookup"><span data-stu-id="3903d-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="3903d-118">Para modificar as configurações de telefone UC no escopo do site, você deve especificar a identidade do site.</span><span class="sxs-lookup"><span data-stu-id="3903d-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="3903d-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3903d-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="3903d-120">Você também pode usar o comando a seguir para modificar simultaneamente todas as suas configurações de telefone UC:</span><span class="sxs-lookup"><span data-stu-id="3903d-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="3903d-121">Se você preferir fazer essa alteração usando o painel de controle do Lync Server, inicie o painel de controle e, em seguida, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="3903d-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="3903d-122">Clique em **clientes** e em **configuração de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3903d-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="3903d-123">Na guia **configuração de dispositivo** , clique duas vezes na coleção de configurações que você deseja modificar (por exemplo, **global**).</span><span class="sxs-lookup"><span data-stu-id="3903d-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="3903d-124">Na caixa de diálogo **Editar configuração de dispositivo** , defina o valor da **caixa QoS (qualidade de serviço) de voz** como **46** e clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3903d-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="3903d-125">Se você tiver várias coleções, será necessário repetir esse processo para cada conjunto de configurações de telefone UC.</span><span class="sxs-lookup"><span data-stu-id="3903d-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="3903d-126">O painel de controle do Lync Server não permitirá que você modifique simultaneamente várias coleções de configurações.</span><span class="sxs-lookup"><span data-stu-id="3903d-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="3903d-127">Se você tiver dispositivos que não são baseados no sistema operacional Windows (por exemplo, iPhones) em sua organização, esses dispositivos não serão afetados alterando a configuração VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="3903d-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="3903d-128">Se você quiser alterar os valores de DSCP nesses dispositivos, será necessário consultar o manual de administração para cada um dos seus tipos de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3903d-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

