---
title: Adicionar IP Interno de Servidor de Borda 2010
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.
---

# <a name="add-edge-server-internal-ip-2010"></a>Adicionar IP Interno de Servidor de Borda 2010

Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.

Esse FQDN especificado deve ser idêntico ao nome do computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Portanto, é necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda que não faz parte de um domínio. Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).