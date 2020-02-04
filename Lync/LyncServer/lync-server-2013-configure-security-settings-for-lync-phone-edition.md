---
title: 'Lync Server 2013: definir configurações de segurança para o Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="ecef7-102">Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecef7-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecef7-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ecef7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ecef7-104">Ajude a melhorar a segurança dos dispositivos que executam o Lync Phone Edition por meio da configuração de segurança SIP e das configurações de bloqueio de telefone.</span><span class="sxs-lookup"><span data-stu-id="ecef7-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="ecef7-105">Para definir as configurações de segurança do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ecef7-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="ecef7-106">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ecef7-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ecef7-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ecef7-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ecef7-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ecef7-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ecef7-109">Na barra de navegação à esquerda, clique em **clientes**e em **configuração de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ecef7-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="ecef7-110">Na página **configuração de dispositivo** , na lista de configurações de dispositivo, clique duas vezes na configuração para a qual você deseja alterar as configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="ecef7-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="ecef7-111">Em **Editar configuração de dispositivo**, na **segurança SIP**, especifique o nível de segurança SIP.</span><span class="sxs-lookup"><span data-stu-id="ecef7-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="ecef7-112">O nível padrão é **alto**, o que recomendamos usar.</span><span class="sxs-lookup"><span data-stu-id="ecef7-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="ecef7-113">Em **Editar configuração de dispositivo**, em **bloqueio de telefone**, marque ou desmarque a caixa de seleção **impor bloqueio de dispositivo** (marcada por padrão) e especifique o comprimento mínimo do PIN (6 caracteres por padrão) e período de tempo limite (10 minutos por padrão).</span><span class="sxs-lookup"><span data-stu-id="ecef7-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="ecef7-114">Recomendamos usar esses padrões ou aumentar o comprimento do PIN e/ou reduzir o período de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="ecef7-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecef7-115">Para obter detalhes, consulte <A href="lync-server-2013-enforce-phone-locking.md">reforçar o bloqueio de telefone no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ecef7-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ecef7-116">Definir configurações de segurança para os telefones do Lync Phone Edition usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecef7-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ecef7-117">As configurações de segurança podem ser gerenciadas usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ecef7-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="ecef7-118">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ecef7-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ecef7-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="ecef7-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="ecef7-120">Para modificar o modo de segurança SIP</span><span class="sxs-lookup"><span data-stu-id="ecef7-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="ecef7-121">Esse comando define o SIPSecurityMode para o conjunto global de configurações de telefone UC para médio.</span><span class="sxs-lookup"><span data-stu-id="ecef7-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="ecef7-122">A segurança SIP também pode ser definida como baixa ou alta (o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="ecef7-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="ecef7-123">Para modificar o comprimento mínimo do PIN</span><span class="sxs-lookup"><span data-stu-id="ecef7-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="ecef7-124">Neste exemplo, todas as configurações de telefone UC são modificadas para exigir um comprimento mínimo de PIN de 7 dígitos.</span><span class="sxs-lookup"><span data-stu-id="ecef7-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="ecef7-125">Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ecef7-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ecef7-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="ecef7-126">See Also</span></span>


[<span data-ttu-id="ecef7-127">Gerenciando a autenticação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecef7-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="ecef7-128">Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecef7-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

