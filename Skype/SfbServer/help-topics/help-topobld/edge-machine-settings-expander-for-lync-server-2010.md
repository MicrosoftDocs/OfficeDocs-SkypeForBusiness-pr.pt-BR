---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades dos computadores do Servidor de Borda como um único Servidor de Borda ou como computadores membros em um pool de Borda, você define as definições de configuração do nome do servidor e do endereço IP:'
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807131"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6bce7-103">Expansor de Configurações de Máquina de Borda para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6bce7-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="6bce7-104">Para editar as propriedades dos computadores do Servidor de Borda como um único Servidor de Borda ou como computadores membros em um pool de Borda, você define as definições de configuração do nome do servidor e **do endereço IP:**</span><span class="sxs-lookup"><span data-stu-id="6bce7-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="6bce7-105">**Nome interno ou FQDN**: digite o nome do computador da forma como ele é chamado pelo DNS.</span><span class="sxs-lookup"><span data-stu-id="6bce7-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="6bce7-106">**Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede (NIC) interna desse computador.</span><span class="sxs-lookup"><span data-stu-id="6bce7-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="6bce7-107">Configure o endereço **IPv4** **externo do** serviço de Borda de Acesso associado a este computador</span><span class="sxs-lookup"><span data-stu-id="6bce7-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6bce7-108">Se você selecionou usar um único endereço IP para a configuração do Servidor de Borda, só poderá editar o endereço IPv4 externo para o serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="6bce7-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="6bce7-109">Os outros serviços de Borda compartilharão o mesmo endereço IPv4 que o serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="6bce7-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="6bce7-110">Se disponível para edição, configure o endereço **IPv4** externo do serviço de **Webconferência** associado a este computador</span><span class="sxs-lookup"><span data-stu-id="6bce7-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="6bce7-111">Se estiver disponível para edição, configure o endereço **IPv4** externo do serviço de Borda **A/V** associado a este computador</span><span class="sxs-lookup"><span data-stu-id="6bce7-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="6bce7-112">Se estiver disponível para editar, configure o **Endereço IPv4 público habilitado por NAT** associado a esse computador.</span><span class="sxs-lookup"><span data-stu-id="6bce7-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6bce7-113">A propriedade de configuração do endereço **IPv4** público habilitado para NAT só estará disponível para edição se você optar por fornecer NAT (conversão de endereço de rede) para o serviço de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6bce7-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="6bce7-114">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6bce7-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="6bce7-115">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6bce7-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="6bce7-116">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="6bce7-116">**Help** Displays this help screen.</span></span>
  

