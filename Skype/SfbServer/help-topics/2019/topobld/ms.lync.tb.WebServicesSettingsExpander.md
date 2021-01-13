---
title: Expansor de Configurações de Serviços da Web
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: No Construtor de Topologias, você pode modificar as configurações de porta usadas para seus serviços Web internos e externos. Além disso, se você estiver implantando o balanceamento de carga DNS (Sistema de Nomes de Domínio), poderá usar o Construtor de Topologias para configurar o FQDN (nome de domínio totalmente qualificado) do pool que é resolvido para os endereços IP físicos de todos os servidores nesse pool.
ms.openlocfilehash: 99f052ebbfc4199f077744eee444333822075c24
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800691"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="cffef-104">Expansor de Configurações de Serviços da Web</span><span class="sxs-lookup"><span data-stu-id="cffef-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="cffef-105">No Construtor de Topologias, você pode modificar as configurações de porta usadas para seus serviços Web internos e externos.</span><span class="sxs-lookup"><span data-stu-id="cffef-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="cffef-106">Além disso, se você estiver implantando o balanceamento de carga DNS (Sistema de Nomes de Domínio), poderá usar o Construtor de Topologias para configurar o FQDN (nome de domínio totalmente qualificado) do pool que é resolvido para os endereços IP físicos de todos os servidores nesse pool.</span><span class="sxs-lookup"><span data-stu-id="cffef-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="cffef-107">Editando Definições de Serviços Web</span><span class="sxs-lookup"><span data-stu-id="cffef-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="cffef-108">Selecione o servidor Front-Ends Standard Edition ou o pool de Front-Ends Enterprise Edition apropriado e então clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cffef-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="cffef-109">Na caixa de diálogo **Editar Propriedades**, clique na guia **Serviços Web**.</span><span class="sxs-lookup"><span data-stu-id="cffef-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cffef-110">Se você tiver mais de um pool de Front-End ou Servidor Front-End, o FQDN de serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="cffef-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="cffef-111">Por exemplo, se você definir o FQDN de serviços Web externos de um Servidor front-end como **pool01.contoso.com**, não poderá usar o **pool01.contoso.com** para outro pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="cffef-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="cffef-112">Se você também estiver implantando Diretores, o FQDN de serviços Web externos definido para qualquer Diretor ou pool de Diretores deverá ser exclusivo de qualquer outro Diretor ou pool de Diretores, bem como de qualquer pool de Front-End ou Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="cffef-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="cffef-113">Se você decidir substituir os serviços Web internos por um FQDN autodefina, cada FQDN deverá ser exclusivo de qualquer outro pool de Front-End, Diretor ou pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="cffef-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="cffef-114">Caso esteja editando as propriedades de um pool Enterprise Edition, você terá a opção de escolher **Substituir FQDN**.</span><span class="sxs-lookup"><span data-stu-id="cffef-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="cffef-115">Esta opção deve ser selecionada apenas caso esteja usando balanceamento de carga DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="cffef-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="cffef-116">Se estiver usando balanceamento de carga DNS, selecione **Substituir FQDN** e, na caixa de texto, digite o FQDN do pool que resolve para todos os endereços IP físicos dos servidores no pool em questão.</span><span class="sxs-lookup"><span data-stu-id="cffef-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="cffef-117">Caso não esteja usando balanceamento de carga DNS e não selecionar **Substituir FQDN**, você não poderá alterar o FQDN dos serviços web internos.</span><span class="sxs-lookup"><span data-stu-id="cffef-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="cffef-118">O FQDN de serviços Web internos é a URL usada por usuários internos para se conectar ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cffef-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="cffef-p105">Insira, opcionalmente, novos valores HTTP, HTTPS ou HTTP e HTTPS para as **Portas de escuta** e as **Portas publicadas**. Portas de escuta são as portas usadas pelos IIS (Internet Information Services) para escutar por tráfego SIP (Session Initiation Protocol) de entrada; portas publicadas são portas configuradas em um balanceador de carga ou servidor de proxy reverso e também são usadas para escutar o tráfego SIP de entrada. Por padrão, tanto a porta de escuta HTTP quanto a porta publicada HTTP estão definidas à porta 80; as portas HTTPS correspondentes estão ambas definidas à 443. O valor padrão para as duas portas publicadas HTTP é 8080 e as portas HTTPS correspondentes estão definidas como 4443.</span><span class="sxs-lookup"><span data-stu-id="cffef-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="cffef-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cffef-123">Click **OK**.</span></span>
    
<span data-ttu-id="cffef-124">Caso você modifique o FQDN interno ou qualquer uma das atribuições de porta de escuta, você deve executar novamente uma configuração local em todos os servidores no pool para que essas mudanças tenham efeito.</span><span class="sxs-lookup"><span data-stu-id="cffef-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

