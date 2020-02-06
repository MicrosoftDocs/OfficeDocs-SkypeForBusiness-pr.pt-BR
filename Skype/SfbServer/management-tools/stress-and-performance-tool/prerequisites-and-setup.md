---
title: Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business
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
description: Exigências e pré-requisitos da Ferramenta de Stress and Performance do Skype for Business Server 2015. Como instalar e configurar a Ferramenta de Stress and Performance.
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816170"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business
 
Exigências e pré-requisitos da Ferramenta de Stress and Performance do Skype for Business Server 2015. Como instalar e configurar a Ferramenta de Stress and Performance.
  
Antes de executar a Ferramenta de Stress and Performance, saiba quais são os requisitos de hardware, software e configuração do sistema lendo as seguintes seções:
  
- [Requisitos de hardware do cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software do cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuração](prerequisites-and-setup.md#ConfigReqs)
    
Além disso, disponibilizamos, abaixo, a seção [Instalação da Ferramenta de Stress and Performance do Skype for Business Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware do cliente
<a name="ClientHardwareReqs"> </a>

Quando você executar a Ferramenta de Stress and Performance no Skype for Business Server 2015, estes requisitos de hardware deverão ser atendidos, no mínimo, para cada 4500 usuários em seu teste:
  
- Adaptador rede de 1 gigabit
    
- 8 GB RAM
    
- 2 CPUs dual-core
    
## <a name="client-software-requirements"></a>Requisitos de software do cliente
<a name="ClientSoftwareReqs"> </a>

Os sistemas operacionais compatíveis com a Ferramenta de Stress and Performance são:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Além disso, os computadores precisam atender aos seguintes requisitos de software:
  
- O Microsoft .NET 4.5 Framework deverá estar instalado. [Baixe a estrutura .NET 4,5 aqui.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- O recurso Experiência desktop deverá estar habilitado no Windows.
    
- O Microsoft Visual C++ 2013 (x64) deverá estar instalado. [Baixe o Visual C++ 2013 aqui](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- O Skype for Business Server 2015 deverá estar devidamente implantado.
    
## <a name="configuration-requirements"></a>Requisitos de configuração
<a name="ConfigReqs"> </a>

Você precisará dessas configurações adicionais para executar corretamente a Ferramenta de Stress and Performance:
  
- Você deve fazer logon no servidor como membro do grupo do Domínio ou Administrador Local.
    
- Você não pode instalar a ferramenta de Criação de usuário do Skype for Business Server 2015 (UserProvisioningTool.exe) em um servidor Front End ou Standard Edition no qual as contas de usuários ficarão armazenadas.
    
- Quando a ferramenta Criação de Usuário é executada várias vezes, cada usuário que estiver habilitado para o Microsoft Unified Communications precisa ter um número de telefone exclusivo.
    
- O tamanho do arquivo da página precisa ser gerenciado pelos sistemas ou ter pelo menos 1,5 vez a quantidade de RAM do sistema do computador.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalação da Ferramenta de Stress and Performance do Skype for Business Server 2015
<a name="Installing"> </a>

A instalação não poderia ser mais simples. Você precisa executar o arquivo do instalador do Windows, **CapacityPlanningTool.msi**, em cada computador cliente que você utilizará para simular o tráfego de usuários e em um Servidor Front-End em cada pool onde você criará usuários e contatos.
  
Para baixar o. msi, juntamente com os scripts de exemplo mencionados em nossos outros artigos, acesse o link do centro de download: [Skype for Business Server 2015, stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

