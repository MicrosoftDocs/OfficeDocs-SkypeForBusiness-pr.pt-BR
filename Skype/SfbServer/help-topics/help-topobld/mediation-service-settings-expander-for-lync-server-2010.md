---
title: Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:'
ms.openlocfilehash: c0057157168667ea9ed0981390e59d5dfb1cd89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285635"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="eacfc-103">Expansor de Configurações do Serviço de Mediação para o Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="eacfc-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="eacfc-104">Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="eacfc-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="eacfc-p101">**Portas de escuta**: defina a porta **TLS** na qual o serviço de Mediação escutará. Por padrão, o valor da porta é TCP 5067 sobre o protocolo TLS</span><span class="sxs-lookup"><span data-stu-id="eacfc-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="eacfc-p102">Como opção, você define um valor de porta **TCP**. Por padrão, o valor é TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="eacfc-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eacfc-p103">A configuração do valor de porta TCP é habilitada selecionando **Habilitar porta TCP**. Consulte a documentação de seu Gateway PSTN (Rede Telefônica Pública Comutada) ou IP-PBX (Internet Protocol Private Branch Exchange) para os requisitos de configurações de porta necessários para se comunicar com o serviço de Mediação.</span><span class="sxs-lookup"><span data-stu-id="eacfc-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="eacfc-111">Você deve **Habilitar porta TCP** para definir o valor de porta para as comunicações TCP a partir de seu gateway PSTN ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="eacfc-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="eacfc-112">Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).</span><span class="sxs-lookup"><span data-stu-id="eacfc-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="eacfc-p104">Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, selecione um novo o padrão e clique em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="eacfc-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="eacfc-116">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eacfc-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="eacfc-117">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eacfc-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="eacfc-118">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="eacfc-118">**Help** Displays this help screen.</span></span>
  

