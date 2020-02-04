---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'O assistente definir novo Office Web Apps Server define um novo servidor do Office Web Apps na sua implantação. Preencha as seguintes informações:'
ms.openlocfilehash: 2af737d2579fb4d89c6670e016ff89a8d24f3743
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685084"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="9689f-104">Adicionar Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="9689f-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="9689f-105">O assistente **definir novo Office Web Apps Server** define um novo servidor do Office Web Apps na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="9689f-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="9689f-106">Preencha as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9689f-106">You fill in the following information:</span></span>

 <span data-ttu-id="9689f-107">**Office Web Apps Server FQDN**: digite o nome de domínio totalmente qualificado do servidor que hospedará o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="9689f-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="9689f-108">**URL de descoberta do servidor do Office Web Apps**: digite a URL (Uniform Resource Locator) completa do servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="9689f-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="9689f-109">O comportamento padrão da **URL de descoberta do Office Web Apps Server** é criar a URL com base no FQDN do servidor do Office Web Apps no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="9689f-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="9689f-110">Na maioria dos casos, não será preciso alterar o formato padrão.</span><span class="sxs-lookup"><span data-stu-id="9689f-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="9689f-111">Talvez seja necessário alterar o formato padrão no caso de o servidor do Office Web Apps e da URL de descoberta do Office Web Apps Server devem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="9689f-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="9689f-112">Por exemplo, seu servidor do Office Web Apps é colocado na rede de perímetro e terá uma URL diferente com base no local.</span><span class="sxs-lookup"><span data-stu-id="9689f-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="9689f-113">O **Office Web Apps Server é implantado em uma rede externa (ou seja, perímetro/Internet)**: marque a caixa de seleção se o servidor do Office Web Apps estiver fora do seu firewall interno, como a rede de perímetro, a rede externa ou outra zona de rede que não seja igual à sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="9689f-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="9689f-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="9689f-114">See also</span></span>

[<span data-ttu-id="9689f-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="9689f-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
