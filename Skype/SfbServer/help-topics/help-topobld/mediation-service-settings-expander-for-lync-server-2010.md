---
title: Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Edite as propriedades do serviço de mediação definindo as seguintes propriedades:'
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215102"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fa22c-103">Expansor de Configurações do Serviço de Mediação para o Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fa22c-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="fa22c-104">Edite as propriedades do serviço de mediação definindo as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="fa22c-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="fa22c-105">**Portas de escuta**: defina a porta **TLS** que o serviço de mediação escutará.</span><span class="sxs-lookup"><span data-stu-id="fa22c-105">**Listening ports**: Define the **TLS** port that the Mediation service will listen on.</span></span> <span data-ttu-id="fa22c-106">Por padrão, o valor da porta é TCP 5067 sobre a segurança da camada de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="fa22c-106">By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="fa22c-107">Opcionalmente, você define um valor de porta **TCP** .</span><span class="sxs-lookup"><span data-stu-id="fa22c-107">Optionally, you define a **TCP** port value.</span></span> <span data-ttu-id="fa22c-108">Por padrão, o valor é TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="fa22c-108">By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa22c-109">A configuração do valor da porta TCP é habilitada selecionando **habilitar porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="fa22c-109">The TCP port value setting is enabled by selecting **Enable TCP port**.</span></span> <span data-ttu-id="fa22c-110">Você deve consultar a documentação do seu gateway PSTN (rede telefônica pública comutada) ou do protocolo IP para os requisitos das configurações de porta necessárias para se comunicar com o serviço de mediação.</span><span class="sxs-lookup"><span data-stu-id="fa22c-110">You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="fa22c-111">Você **habilita a porta TCP** para definir o valor de porta para as comunicações TCP do seu gateway PSTN ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fa22c-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="fa22c-112">Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).</span><span class="sxs-lookup"><span data-stu-id="fa22c-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="fa22c-p104">Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="fa22c-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="fa22c-116">**OK** aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fa22c-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="fa22c-117">**Cancelar** descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fa22c-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="fa22c-118">**Ajuda** exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="fa22c-118">**Help** Displays this help screen.</span></span>
  

