---
title: Expansor de Configurações de Registrador para o Lync Server for 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Edite as configurações para resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: 5ed1311e73ea035b7672ba75bab337c9212e8816
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282235"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="aee0d-103">Expansor de Configurações de Registrador para o Lync Server for 2010</span><span class="sxs-lookup"><span data-stu-id="aee0d-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="aee0d-104">Edite as configurações para **resiliência** e configure as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="aee0d-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="aee0d-105">Selecione o pool de registradores de **backup associado** na lista.</span><span class="sxs-lookup"><span data-stu-id="aee0d-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="aee0d-106">Opcionalmente, marque a caixa de seleção **failover automático e failback para voz** .</span><span class="sxs-lookup"><span data-stu-id="aee0d-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="aee0d-107">Configurar o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**.</span><span class="sxs-lookup"><span data-stu-id="aee0d-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="aee0d-108">Por padrão, os intervalos são de 120 segundos para a detecção de falha de voz e 240 segundos para failback de voz.</span><span class="sxs-lookup"><span data-stu-id="aee0d-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="aee0d-109">O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="aee0d-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="aee0d-110">Definir o intervalo como baixo (ou seja, menos de 120 segundos) ou o failover e o failback definidos com mais detalhes podem resultar no failover real e o failback não funcionando como esperado.</span><span class="sxs-lookup"><span data-stu-id="aee0d-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="aee0d-111">**OK** Aceita e confirma as alterações na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aee0d-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="aee0d-112">**Cancelar** Descarta as alterações e fecha a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aee0d-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="aee0d-113">**Ajuda** Exibe essa tela de ajuda.</span><span class="sxs-lookup"><span data-stu-id="aee0d-113">**Help** Displays this help screen.</span></span>
  

