---
title: 'Lync Server 2013: impor o bloqueio de telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4961aabf2edce33f1e5975497844704ac0feae03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="671fb-102">Impor o bloqueio de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671fb-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="671fb-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="671fb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="671fb-104">Os dispositivos do Lync Phone Edition podem ser bloqueados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="671fb-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="671fb-105">Se você aplicar o bloqueio de telefone, o dispositivo que executa o Lync Phone Edition será bloqueado após um período de tempo que você configurar.</span><span class="sxs-lookup"><span data-stu-id="671fb-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="671fb-106">Quando um telefone está bloqueado, um usuário pode fazer chamadas, mas não pode acessar o calendário e informações de contato, caixa postal ou logs de chamadas ou usar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="671fb-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="671fb-107">Para desbloquear o telefone, o usuário insere um PIN.</span><span class="sxs-lookup"><span data-stu-id="671fb-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="671fb-108">Para impor o bloqueio de telefone, habilite e configure-o usando o painel de controle do Lync Server ou cmdlets do PowerShell do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="671fb-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="671fb-109">Você pode impor o bloqueio de telefone globalmente ou somente dentro do site para o qual ele está configurado.</span><span class="sxs-lookup"><span data-stu-id="671fb-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="671fb-110">Para configurar e impor o bloqueio do telefone</span><span class="sxs-lookup"><span data-stu-id="671fb-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="671fb-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="671fb-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="671fb-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="671fb-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="671fb-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="671fb-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="671fb-114">Clique em **clientes**e em **configuração de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="671fb-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="671fb-115">Na guia **configuração de dispositivo** , na lista de configurações de dispositivo, clique duas vezes na configuração para a qual você deseja alterar as configurações de bloqueio de telefone.</span><span class="sxs-lookup"><span data-stu-id="671fb-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="671fb-116">Na caixa de diálogo **Editar configuração de dispositivo** , verifique se a caixa de seleção **impor bloqueio de dispositivo** está marcada.</span><span class="sxs-lookup"><span data-stu-id="671fb-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="671fb-117">No **comprimento mínimo do PIN**, aceite o valor padrão para o número mínimo de dígitos que o PIN de desbloqueio deve conter ou especifique um novo valor.</span><span class="sxs-lookup"><span data-stu-id="671fb-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="671fb-118">O intervalo para o comprimento do pino é de quatro a 15 dígitos, e o padrão é seis.</span><span class="sxs-lookup"><span data-stu-id="671fb-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="671fb-119">Em **tempo limite de bloqueio de telefone**, aceite o valor padrão pelo período de tempo mínimo antes de o telefone bloquear a si mesmo ou especifique um novo valor.</span><span class="sxs-lookup"><span data-stu-id="671fb-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="671fb-120">O intervalo para o tempo limite é de 0 a 60 minutos, e o padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="671fb-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="671fb-121">Insira o valor no formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="671fb-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="671fb-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="671fb-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="671fb-123">Impondo o bloqueio de telefone usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="671fb-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="671fb-124">O bloqueio de telefone pode ser imposto usando o cmdlet Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="671fb-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="671fb-125">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="671fb-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="671fb-126">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="671fb-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="671fb-127">Para ativar o bloqueio de telefone</span><span class="sxs-lookup"><span data-stu-id="671fb-127">To enable phone locking</span></span>

  - <span data-ttu-id="671fb-128">O comando a seguir habilita o bloqueio por telefone para o site Redmond.</span><span class="sxs-lookup"><span data-stu-id="671fb-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="671fb-129">Para desativar o bloqueio de telefone, defina a propriedade EnforcePhoneLock como false ($False).</span><span class="sxs-lookup"><span data-stu-id="671fb-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="671fb-130">Para ativar o bloqueio de telefone e modificar o tempo limite do bloqueio do telefone</span><span class="sxs-lookup"><span data-stu-id="671fb-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="671fb-131">Esse comando ativa o bloqueio por telefone e também define o tempo limite do bloqueio do telefone como 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="671fb-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="671fb-132">Para habilitar o bloqueio de telefone em toda a organização</span><span class="sxs-lookup"><span data-stu-id="671fb-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="671fb-133">Neste exemplo, o bloqueio por telefone está habilitado em todas as configurações de configuração de telefone UC em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="671fb-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="671fb-134">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="671fb-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="671fb-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="671fb-135">See Also</span></span>


[<span data-ttu-id="671fb-136">Gerenciando a autenticação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671fb-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="671fb-137">Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="671fb-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

