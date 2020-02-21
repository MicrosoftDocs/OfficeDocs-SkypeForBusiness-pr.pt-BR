---
title: 'Lync Server 2013: configurar definições de segurança para o Lync Phone Edition'
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
ms.openlocfilehash: e91ef78b2aedb3985ef1ab350de43261e4885d87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="a1332-102">Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1332-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1332-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a1332-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a1332-104">Ajuda a melhorar a segurança de dispositivos que executam o Lync Phone Edition através da configuração de segurança SIP e das configurações de bloqueio de telefone.</span><span class="sxs-lookup"><span data-stu-id="a1332-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="a1332-105">Para definir as configurações de segurança para o Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a1332-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="a1332-106">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a1332-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1332-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1332-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1332-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1332-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1332-109">Na barra de navegação esquerda, clique em **Clientes** e em **Configuração dos dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a1332-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="a1332-110">Na página **Configuração de Dispositivo**, na lista de configurações de dispositivo, clique duas vezes na configuração para a qual você deseja alterar as configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="a1332-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="a1332-p102">Em **Editar Configuração dos Dispositivos**, em **Segurança SIP**, especifique o nível de segurança SIP. O nível padrão é **Alto** (recomendado).</span><span class="sxs-lookup"><span data-stu-id="a1332-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="a1332-p103">Em **Editar Configuração dos Dispositivos**, em **Bloqueio de Telefone**, selecione ou desmarque a caixa de seleção **Impor bloqueio de dispositivo** (selecionada por padrão) e especifique o tamanho mínimo do PIN (seis caracteres por padrão) e o período de tempo limite (10 minutos por padrão). Recomendamos usar esses padrões ou aumentar o tamanho do PIN e/ou reduzir o período de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a1332-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1332-115">Para obter detalhes, consulte <A href="lync-server-2013-enforce-phone-locking.md">impor bloqueio de telefone no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a1332-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1332-116">Configurando definições de segurança para o Lync Phone Edition phones usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1332-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1332-117">As configurações de segurança podem ser gerenciadas usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a1332-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="a1332-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1332-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1332-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="a1332-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="a1332-120">Para modificar o modo de segurança SIP</span><span class="sxs-lookup"><span data-stu-id="a1332-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="a1332-p105">Este comando define SIPSecurityMode para o conjunto global de configurações de telefone UC como Médio. A segurança SIP também pode ser definida como Baixo ou Alto (valor padrão).</span><span class="sxs-lookup"><span data-stu-id="a1332-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="a1332-123">Para modificar o tamanho mínimo do PIN</span><span class="sxs-lookup"><span data-stu-id="a1332-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="a1332-124">Neste exemplo, todas as configurações do telefone UC são modificadas para exigir um PIN com tamanho mínimo de sete dígitos.</span><span class="sxs-lookup"><span data-stu-id="a1332-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="a1332-125">Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a1332-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1332-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1332-126">See Also</span></span>


[<span data-ttu-id="a1332-127">Gerenciando a autenticação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1332-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="a1332-128">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1332-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

