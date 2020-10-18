---
title: 'Lync Server 2013: impor bloqueio de telefone'
description: 'Lync Server 2013: impor bloqueio de telefone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575597"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="775f7-103">Impor bloqueio de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="775f7-103">Enforce phone locking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="775f7-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="775f7-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="775f7-105">Os dispositivos do Lync Phone Edition podem ser bloqueados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="775f7-105">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="775f7-106">Se você aplicar o bloqueio de telefone, o dispositivo que executa o Lync Phone Edition é bloqueado após um período de tempo que você configura.</span><span class="sxs-lookup"><span data-stu-id="775f7-106">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="775f7-107">Quando um telefone é bloqueado, um usuário pode fazer chamadas, mas não pode acessar informações de contato, caixa postal ou logs de chamadas ou usar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="775f7-107">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="775f7-108">Para desbloquear o telefone, o usuário insere um PIN.</span><span class="sxs-lookup"><span data-stu-id="775f7-108">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="775f7-109">Para impor o bloqueio de telefone, habilite e configure-o usando o painel de controle do Lync Server ou cmdlets do Lync Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="775f7-109">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="775f7-110">Você pode impor o bloqueio de telefone globalmente ou apenas dentro do site para o qual ele está configurado.</span><span class="sxs-lookup"><span data-stu-id="775f7-110">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="775f7-111">Para configurar e impor o bloqueio de telefone</span><span class="sxs-lookup"><span data-stu-id="775f7-111">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="775f7-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="775f7-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="775f7-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="775f7-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="775f7-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="775f7-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="775f7-115">Clique**Clientes** e em **Configuração do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="775f7-115">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="775f7-116">Na guia **Configuração do Dispositivo**, na lista de configurações do dispositivo, clique duas vezes na configuração de bloqueio do telefone que deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="775f7-116">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="775f7-117">Na caixa de diálogo **Editar Configuração do Dispositivo** verifique se a caixa de seleção **Impor bloqueio do dispositivo** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="775f7-117">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="775f7-118">Em **tamanho mínimo do PIN**, aceite o valor padrão para o número mínimo de dígitos que o PIN de desbloqueio deve conter ou especifique um novo valor.</span><span class="sxs-lookup"><span data-stu-id="775f7-118">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="775f7-119">O intervalo para o comprimento do PIN é de quatro a 15 dígitos e o padrão é seis.</span><span class="sxs-lookup"><span data-stu-id="775f7-119">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="775f7-120">Em **tempo limite de bloqueio de telefone**, aceite o valor padrão para o período de tempo mínimo antes que o telefone seja bloqueado ou especifique um novo valor.</span><span class="sxs-lookup"><span data-stu-id="775f7-120">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="775f7-121">O intervalo para o tempo limite é de 0 a 60 minutos, e o padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="775f7-121">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="775f7-122">Insira o valor no formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="775f7-122">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="775f7-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="775f7-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="775f7-124">Impondo o bloqueio de telefone usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="775f7-124">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="775f7-125">O bloqueio de telefone pode ser imposto usando o cmdlet Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="775f7-125">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="775f7-126">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="775f7-126">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="775f7-127">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="775f7-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="775f7-128">Para habilitar o bloqueio de telefone</span><span class="sxs-lookup"><span data-stu-id="775f7-128">To enable phone locking</span></span>

  - <span data-ttu-id="775f7-129">O seguinte comando habilita o bloqueio de telefone para o site Redmond.</span><span class="sxs-lookup"><span data-stu-id="775f7-129">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="775f7-130">Para desativar o bloqueio de telefone, defina a propriedade EnforcePhoneLock para Falso ($False).</span><span class="sxs-lookup"><span data-stu-id="775f7-130">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="775f7-131">Para habilitar o bloqueio de telefone e modificar o tempo limite de bloqueio do telefone</span><span class="sxs-lookup"><span data-stu-id="775f7-131">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="775f7-132">Este comando habilita o bloqueio de telefone e também define o tempo limite do bloqueio de telefone para 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="775f7-132">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="775f7-133">Para habilitar o bloqueio de telefone em toda a organização</span><span class="sxs-lookup"><span data-stu-id="775f7-133">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="775f7-134">Neste exemplo, o bloqueio de telefone está habilitado em todas as definições de configuração UC em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="775f7-134">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="775f7-135">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="775f7-135">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="775f7-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="775f7-136">See Also</span></span>


[<span data-ttu-id="775f7-137">Gerenciando a autenticação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="775f7-137">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="775f7-138">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="775f7-138">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

