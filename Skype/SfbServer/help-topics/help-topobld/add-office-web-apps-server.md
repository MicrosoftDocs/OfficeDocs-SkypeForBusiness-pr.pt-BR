---
title: Adicionar Servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'O assistente Definir Novo Servidor do Office Web Apps define um novo Servidor do Office Web Apps em sua implantação. Preencha com as seguintes informações:'
ms.openlocfilehash: 002566fb77539745d1d0023159e9af7852b1ecdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119700"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="aeb0d-104">Adicionar Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="aeb0d-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="aeb0d-105">O **assistente Definir Novo Servidor do Office Web Apps** define um novo Servidor do Office Web Apps em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="aeb0d-106">Preencha com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="aeb0d-106">You fill in the following information:</span></span>

 <span data-ttu-id="aeb0d-107">**FQDN** do Servidor do Office Web Apps : Digite o nome de domínio totalmente qualificado do servidor que hospedará o Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="aeb0d-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="aeb0d-108">**URL de** descoberta do Servidor do Office Web Apps : Digite o URL (localizador de recursos uniforme) completo do Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="aeb0d-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="aeb0d-109">O comportamento padrão da URL de descoberta do **Servidor do Office Web Apps** é criar a URL com base no FQDN do Servidor do Office Web Apps no formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="aeb0d-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="aeb0d-110">Na maioria dos casos, não será necessário alterar o formato padrão.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="aeb0d-111">Talvez seja necessário alterar o formato padrão caso o Servidor do Office Web Apps e a URL de descoberta do Servidor do Office Web Apps sejam diferentes.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="aeb0d-112">Por exemplo, seu Servidor do Office Web Apps é colocado na rede de perímetro e terá uma URL diferente com base no local.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="aeb0d-113">Servidor do Office Web Apps é implantado em uma rede externa **(ou seja, perímetro/Internet)**: Marque a caixa de seleção se o Servidor do Office Web Apps for colocado fora do firewall interno, como a rede de perímetro, a rede externa ou outra zona de rede que não seja a mesma da rede interna.</span><span class="sxs-lookup"><span data-stu-id="aeb0d-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeb0d-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="aeb0d-114">See also</span></span>

[<span data-ttu-id="aeb0d-115">Componentes e topologias para conferência</span><span class="sxs-lookup"><span data-stu-id="aeb0d-115">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)