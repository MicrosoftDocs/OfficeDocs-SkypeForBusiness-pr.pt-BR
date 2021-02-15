---
title: Instalar Invocação do Repositório de Configuração Local (Configuração)
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
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para começar a instalação do banco de dados que armazenará a cópia local somente leitura do armazenamento de Gerenciamento Central, selecione entre recuperar a configuração definida publicada usando o Construtor de Topologias do armazenamento de Gerenciamento Central já instalado e configurado ou lendo a configuração definida de outra mídia. Para um computador que está na rede interna da sua organização, selecione Recuperar a configuração automaticamente no Armazenamento de Gerenciamento Central.
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827201"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="12f4f-104">Instalar Invocação do Repositório de Configuração Local (Configuração)</span><span class="sxs-lookup"><span data-stu-id="12f4f-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="12f4f-105">Para começar a instalação do banco de dados que armazenará a cópia local somente leitura do armazenamento de Gerenciamento Central, selecione entre recuperar a configuração definida publicada usando o Construtor de Topologias do armazenamento de Gerenciamento Central já instalado e configurado ou lendo a configuração definida de outra mídia.</span><span class="sxs-lookup"><span data-stu-id="12f4f-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="12f4f-106">Para um computador que está na rede interna da sua organização, selecione Recuperar configuração automaticamente no **Armazenamento de Gerenciamento Central.**</span><span class="sxs-lookup"><span data-stu-id="12f4f-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="12f4f-107">Se você estiver instalando uma réplica do repositório de Gerenciamento Central em um Servidor de Borda, selecione para ler a cópia exportada do documento de configuração da mídia portátil, como uma unidade flash USB, disco rígido USB, CD-ROM ou outra mídia.</span><span class="sxs-lookup"><span data-stu-id="12f4f-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="12f4f-108">Se você estiver instalando o armazenamento de Configuração Local em um Servidor de Borda, as informações de configuração deverão estar em um formato exportado do armazenamento de Gerenciamento Central executando o cmdlet do Windows PowerShell:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="12f4f-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="12f4f-109">Após ter selecionado a opção adequada, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="12f4f-109">After you have selected the appropriate option, click **Next**.</span></span>
  

