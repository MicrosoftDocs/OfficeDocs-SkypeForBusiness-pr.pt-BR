---
title: Pré-requisitos e configuração para a ferramenta de estresse e desempenho do Skype for stress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisitos ou pré-requisitos para a ferramenta de estresse e desempenho do Skype for Business Server 2015. Como instalar ou configurar a ferramenta de estresse e desempenho.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005976"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Pré-requisitos e configuração para a ferramenta de estresse e desempenho do Skype for stress
 
Requisitos ou pré-requisitos para a ferramenta de estresse e desempenho do Skype for Business Server 2015. Como instalar ou configurar a ferramenta de estresse e desempenho.
  
Temos as seguintes seções de requisitos de configuração de hardware, software e sistema que você precisa conhecer antes de executar a ferramenta de estresse e desempenho:
  
- [Requisitos de hardware do cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software do cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuração](prerequisites-and-setup.md#ConfigReqs)
    
Além disso, também temos uma seção abaixo para [instalar a ferramenta de estresse e desempenho do Skype for Business Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware do cliente
<a name="ClientHardwareReqs"> </a>

Ao executar a ferramenta de estresse e desempenho em relação à implantação do Skype for Business Server 2015, você deverá, no mínimo, atender a todos os requisitos de hardware atendidos para cada 4500 usuários no teste:
  
- adaptador de rede de 1 Gigabit
    
- 8 GB de RAM
    
- 2 CPUs de núcleo dual
    
## <a name="client-software-requirements"></a>Requisitos de software do cliente
<a name="ClientSoftwareReqs"> </a>

Os sistemas operacionais compatíveis com a ferramenta de estresse e desempenho são:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Além disso, os computadores precisam atender aos seguintes requisitos de software:
  
- Você precisará do Microsoft .NET 4,5 Framework instalado. [Baixe a estrutura do .NET 4,5 aqui.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Você precisará do recurso experiência Desktop habilitado no Windows.
    
- Você precisará do Microsoft Visual C++ 2013 (x64) instalado. [Baixe o Visual C++ 2013 aqui](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Você precisará do Skype for Business Server 2015 implantado com êxito.
    
## <a name="configuration-requirements"></a>Requisitos de configuração
<a name="ConfigReqs"> </a>

Você precisará dessas configurações adicionais para executar a ferramenta de estresse e desempenho com êxito:
  
- Você precisa fazer logon no servidor como membro do domínio ou do grupo do administrador local.
    
- Você não pode instalar a ferramenta de criação de usuário do Skype for Business Server 2015 (UserProvisioningTool. exe) em qualquer servidor front-end ou servidor Standard Edition onde as contas de usuário residirão.
    
- Quando a ferramenta de criação de usuário é executada várias vezes, cada usuário habilitado para o Microsoft Unified Communications precisa ter um número de telefone exclusivo.
    
- O tamanho do arquivo de paginação deve ser gerenciado por sistemas ou deve ser pelo menos 1,5 vezes a quantidade de RAM no sistema do computador.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalando a ferramenta de estresse e desempenho do Skype for Business Server 2015
<a name="Installing"> </a>

A instalação não pôde ser mais simples. Você precisa executar o arquivo do Windows Installer, **CapacityPlanningTool. msi**, em cada computador cliente que será usado para simular o tráfego do usuário e em um servidor front-end em cada pool onde você criará usuários e contatos.
  
Para baixar o. msi, junto com os exemplos de scripts mencionados em nossos outros artigos, vá para o link do centro de download: [Skype for Business Server 2015, ferramenta de estresse e desempenho](https://www.microsoft.com/download/details.aspx?id=50367).
  

