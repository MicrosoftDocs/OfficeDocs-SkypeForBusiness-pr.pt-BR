---
title: 'Lync Server 2013: usando o portal da Web administrativo do sistema de salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677fdd070994c8cc1f63f775ffb2569642768f0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529938"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="bb8fa-102">Usando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8fa-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb8fa-103">_**Última modificação do tópico:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="bb8fa-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="bb8fa-104">Depois de implantar o LRS no servidor, você pode verificar o status de todas as salas do LRS entrando no portal da Web administrativo do LRS a partir de um navegador.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="bb8fa-105">Entrar</span><span class="sxs-lookup"><span data-stu-id="bb8fa-105">Sign in</span></span>

1.  <span data-ttu-id="bb8fa-106">Navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="bb8fa-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="bb8fa-107">https:// \<fe-server\> /lRS</span><span class="sxs-lookup"><span data-stu-id="bb8fa-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="bb8fa-108">Insira as credenciais para a conta LRSSupport ou uma conta que tenha sido adicionada ao grupo de segurança LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="bb8fa-109">![Tela de entrada do portal de administração do sistema de salas do Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Tela de entrada do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="bb8fa-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="bb8fa-110">Página de resumo do portal Web administrativo do LRS</span><span class="sxs-lookup"><span data-stu-id="bb8fa-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="bb8fa-111">A página de resumo fornece as seguintes informações para todas as salas do LRS implantadas no servidor:</span><span class="sxs-lookup"><span data-stu-id="bb8fa-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="bb8fa-112">**Marca**     O nome personalizado que o administrador fornece à sala.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="bb8fa-113">A marca pode ser definida no portal clicando no nome da sala.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="bb8fa-114">**Health**     O status de integridade da sala, que é derivado do status de integridade de agregação da sala, que é mostrado na seção integridade da página Configurações da sala.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="bb8fa-115">**Próxima reunião**     A data e a hora em que a próxima reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="bb8fa-116">**Versão lRS, fabricante, modelo**     Esses valores são predefinidos no LRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="bb8fa-117">Dependendo do fabricante, esses campos podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="bb8fa-118">**Última atualização**     Exibe a última vez em que a página da Web foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="bb8fa-119">![Exibição resumida do portal de administração do sistema de salas do Lync](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Exibição resumida do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="bb8fa-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="bb8fa-120">Informações de sala do LRS</span><span class="sxs-lookup"><span data-stu-id="bb8fa-120">LRS Room Information</span></span>

<span data-ttu-id="bb8fa-121">A seção informações de sala do portal permite que você visualize e configure salas individuais do LRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="bb8fa-122">Ele contém quatro seções: configurações, detalhes, solução de problemas e integridade.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="bb8fa-123">Configurações</span><span class="sxs-lookup"><span data-stu-id="bb8fa-123">Settings</span></span>

<span data-ttu-id="bb8fa-124">Na seção Configurações, é possível definir a senha, a marca de sala e os níveis de volume padrão para a sala.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="bb8fa-125">Se você definir essas configurações, as alterações serão replicadas somente depois que o console do LRS for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="bb8fa-126">Você verá apenas as configurações de atualizações do sistema para sistemas de salas do Lync que são a versão 15,12 e posterior.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="bb8fa-127">![Configurações de sala do portal de administração do sistema de salas do Lync](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configurações de sala do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="bb8fa-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="bb8fa-128">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bb8fa-128">Details</span></span>

<span data-ttu-id="bb8fa-129">A seção detalhes fornece um resumo somente leitura das configurações da sala de LRS, incluindo: o horário da última atualização; próxima reunião; últimas atualizações, manutenção e calibração; configurações de alto-falante, MIC e campainha padrão; Version URI DO SIP; número de telas e detalhes sobre cada tela; status e atividade.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="bb8fa-130">![Exibição detalhada do portal de administração do sistema de salas do Lync](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Exibição detalhada do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="bb8fa-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="bb8fa-131">Solução de Problemas</span><span class="sxs-lookup"><span data-stu-id="bb8fa-131">Troubleshooting</span></span>

<span data-ttu-id="bb8fa-132">A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="bb8fa-133">Também é possível reiniciar o console do LRS (LRS user interface) ou reiniciar todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="bb8fa-134">Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de máquina do LRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="bb8fa-135">Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="bb8fa-136">A atualização da página fornecerá o status mais recente.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="bb8fa-137">![Log de sala do portal de administração do sistema de salas do Lync](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Log de sala do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="bb8fa-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="bb8fa-138">Integridade</span><span class="sxs-lookup"><span data-stu-id="bb8fa-138">Health</span></span>

<span data-ttu-id="bb8fa-139">A seção integridade fornece uma indicação visual da integridade da conexão do Lync Server, dispositivo de áudio, dispositivo de vídeo, estado de resiliência e dispositivo de tela.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="bb8fa-140">![Integridade da sala do portal de administração do sistema de salas do Lync](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integridade da sala do portal de administração do sistema de salas do Lync")</span><span class="sxs-lookup"><span data-stu-id="bb8fa-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="bb8fa-141">Observações adicionais sobre o portal da Web administrativo</span><span class="sxs-lookup"><span data-stu-id="bb8fa-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="bb8fa-142">As alterações de configuração são aplicadas somente após a reinicialização do sistema do LRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="bb8fa-143">Se a senha da conta LRSApp expirar, você não poderá ver o status das salas.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="bb8fa-144">Configure a senha da conta LRSAppuser para que ela nunca expire ou atualize a senha quando estiver próxima de expirar.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="bb8fa-145">O portal da Web administrativo do LRS tem suporte apenas para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bb8fa-146">Perguntas Frequentes</span><span class="sxs-lookup"><span data-stu-id="bb8fa-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="bb8fa-147">Por que não consigo entrar no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="bb8fa-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="bb8fa-148">Ao abrir https://localhost/lrs o, você poderá ver a página de entrada, mas quando digitar suas credenciais, não poderá entrar.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="bb8fa-149">Nesse caso, você deve abrir https://FQDNofFEserver/lrs o para entrar no portal da Web administrativo.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="bb8fa-150">Se o computador a partir do qual você está acessando o portal da Web administrativo estiver em um grupo de trabalho, "http://" não funcionará.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="bb8fa-151">Em vez disso, use "https".</span><span class="sxs-lookup"><span data-stu-id="bb8fa-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="bb8fa-152">Por que não consigo ver LRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="bb8fa-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="bb8fa-153">Verifique se você tem contas do LRS em sua implantação e se elas foram criadas de acordo com as recomendações de implantação do portal da Web administrativo do LRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="bb8fa-154">Certifique-se de que as contas do LRS são provisionadas usando enable-CsMeetingRoom, não Enable-CsUser, no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="bb8fa-155">Se você tiver criado contas do LRS e não puder ver as contas no portal da Web administrativo, colete os logs do servidor usando a ferramenta de registro em log do Lync Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato de suporte do lRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="bb8fa-156">Por que não consigo ver o status do LRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="bb8fa-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="bb8fa-157">Verifique se a conta de usuário LRSApp está habilitada para SIP.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="bb8fa-158">Se você ainda estiver tendo problemas, colete o arquivo **trace. log** no sistema LRS de D: \\ rastreamento \\ LRSAdminLogs \\ e envie-o para o seu contato de suporte do lRS.</span><span class="sxs-lookup"><span data-stu-id="bb8fa-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

