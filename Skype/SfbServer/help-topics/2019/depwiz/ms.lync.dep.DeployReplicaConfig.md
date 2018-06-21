---
title: Instalar repositório de configuração Local invocar (configuração)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Para iniciar a instalação do banco de dados que acomodará a cópia local de somente leitura do repositório de gerenciamento Central, selecione entre recuperar a configuração definida publicada usando o construtor de topologias da Central já instalado e configurado Repositório de gerenciamento ou ler a configuração definida de outra mídia. Para um computador que esteja na rede interna da sua organização, selecione recuperar configuração automaticamente do repositório de gerenciamento Central.
ms.openlocfilehash: 4a061ddec04e2b80412b8e60badb8600633093d9
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979999"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Instalar repositório de configuração Local invocar (configuração)
 
Para iniciar a instalação do banco de dados que acomodará a cópia local de somente leitura do repositório de gerenciamento Central, selecione entre recuperar a configuração definida publicada usando o construtor de topologias da Central já instalado e configurado Repositório de gerenciamento ou ler a configuração definida de outra mídia. Para um computador que esteja na rede interna da sua organização, selecione **recuperar configuração automaticamente do repositório de gerenciamento Central**.
  
Se você estiver instalando uma réplica do repositório de gerenciamento Central em um servidor de borda, selecione ler a cópia exportada do documento configuração de mídia portátil, como uma unidade flash USB, USB do disco rígido, CD-ROM ou outra mídia. 
  
> [!IMPORTANT]
> Se você estiver instalando o repositório de configuração Local em um servidor de borda, as informações de configuração deve estar em um formato que foram exportado de gerenciamento Central armazenam executando o cmdlet do Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Depois de ter selecionado a opção apropriada, clique em **Avançar**.
  

