---
title: Instalar Invocação do Repositório de Configuração Local (Configuração)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para começar a instalação do banco de dados que manterá a cópia somente leitura local do repositório de gerenciamento central, selecione entre recuperar a configuração definida publicada usando o construtor de topologias a partir do centro já instalado e configurado Repositório de gerenciamento ou leitura da configuração definida de outras mídias. Para um computador que esteja na rede interna da sua organização, selecione recuperar configuração automaticamente no repositório de gerenciamento central.
ms.openlocfilehash: 7638ab56e2ddcc8951ae989de11e72e0817a20bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823635"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar Invocação do Repositório de Configuração Local (Configuração)
 
Para começar a instalação do banco de dados que manterá a cópia somente leitura local do repositório de gerenciamento central, selecione entre recuperar a configuração definida publicada usando o construtor de topologias a partir do centro já instalado e configurado Repositório de gerenciamento ou leitura da configuração definida de outras mídias. Para um computador que esteja na rede interna da sua organização, selecione **recuperar configuração automaticamente no repositório de gerenciamento central**.
  
Se você estiver instalando uma réplica do repositório de gerenciamento central em um servidor de borda, selecione para ler a cópia exportada do documento de configuração de mídias portáteis, como uma unidade flash USB, unidade de disco rígido USB, CD-ROM ou outra mídia. 
  
> [!IMPORTANT]
> Se você estiver instalando o repositório de configuração local em um servidor de borda, as informações de configuração deverão estar em um formato que foi exportado do repositório de gerenciamento central executando o cmdlet do Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Depois de selecionar a opção apropriada, clique em **Avançar**.
  

