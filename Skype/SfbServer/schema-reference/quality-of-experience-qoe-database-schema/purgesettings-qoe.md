---
title: Tabela PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade de experiência defasados serão excluídos automaticamente do banco de dados de QoE. Observe que as informações relacionadas à purga também podem ser obtidas de dentro do Shell de Gerenciamento do Skype for Business Server executando o seguinte comando:'
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815801"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="09537-104">Tabela PurgeSettings (QoE)</span><span class="sxs-lookup"><span data-stu-id="09537-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="09537-105">A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade de experiência defasados serão excluídos automaticamente do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="09537-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="09537-106">Observe que as informações relacionadas à purga também podem ser obtidas de dentro do Shell de Gerenciamento do Skype for Business Server executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="09537-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="09537-107">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09537-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="09537-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="09537-108">**Column**</span></span>|<span data-ttu-id="09537-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="09537-109">**Data Type**</span></span>|<span data-ttu-id="09537-110">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="09537-110">**Key/Index**</span></span>|<span data-ttu-id="09537-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="09537-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09537-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="09537-112">**ID**</span></span> <br/> |<span data-ttu-id="09537-113">int</span><span class="sxs-lookup"><span data-stu-id="09537-113">int</span></span>  <br/> |<span data-ttu-id="09537-114">Primário</span><span class="sxs-lookup"><span data-stu-id="09537-114">Primary</span></span>  <br/> |<span data-ttu-id="09537-115">Identificador exclusivo do conjunto de configurações de limpeza de QoE.</span><span class="sxs-lookup"><span data-stu-id="09537-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="09537-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="09537-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="09537-117">bit</span><span class="sxs-lookup"><span data-stu-id="09537-117">bit</span></span>  <br/> ||<span data-ttu-id="09537-118">Quando definido como True (1), o Microsoft Lync Server 2013 limpará periodicamente os registros desatualizados do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="09537-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="09537-119">A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="09537-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="09537-120">Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="09537-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="09537-121">O valor padrão é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="09537-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="09537-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="09537-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="09537-123">int</span><span class="sxs-lookup"><span data-stu-id="09537-123">int</span></span>  <br/> ||<span data-ttu-id="09537-p104">Especifica a idade dos registros de QoE (em dias) que serão limpados do banco de dados: se a limpeza estiver ativada, os registros de QoE mais antigos que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="09537-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="09537-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="09537-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="09537-127">int</span><span class="sxs-lookup"><span data-stu-id="09537-127">int</span></span>  <br/> ||<span data-ttu-id="09537-p105">Especifica a hora local do dia em que a limpeza ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00). Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00).</span><span class="sxs-lookup"><span data-stu-id="09537-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

