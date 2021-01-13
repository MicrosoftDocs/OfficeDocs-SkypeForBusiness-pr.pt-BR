---
title: Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Busines
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Requisitos ou pré-requisitos para a Ferramenta de Stress and Performance do Skype for Business Server 2015. Como instalar ou configurar a Ferramenta de Stress and Performance.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814951"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Busines
 
Requisitos ou pré-requisitos para a Ferramenta de Stress and Performance do Skype for Business Server 2015. Como instalar ou configurar a Ferramenta de Stress and Performance.
  
Temos as seguintes seções de requisitos de configuração de hardware, software e sistema que você precisará estar ciente antes de executar a Ferramenta de Stress and Performance:
  
- [Requisitos de hardware do cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software do cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuração](prerequisites-and-setup.md#ConfigReqs)
    
Além disso, também temos uma seção abaixo para Instalar a Ferramenta de Stress and Performance do [Skype for Business Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware do cliente
<a name="ClientHardwareReqs"> </a>

Ao executar a Ferramenta de Stress and Performance em sua implantação do Skype for Business Server 2015, você precisará, no mínimo, desses requisitos de hardware atendidos para cada 4500 usuários em seu teste:
  
- Adaptador de rede de 1 gigabit
    
- 8 GB de RAM
    
- 2 CPUs dual-core
    
## <a name="client-software-requirements"></a>Requisitos de software do cliente
<a name="ClientSoftwareReqs"> </a>

Os sistemas operacionais com suporte para a Ferramenta de Stress and Performance são:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Além disso, os computadores precisam atender aos seguintes requisitos de software:
  
- Você precisará ter o Microsoft .NET 4.5 Framework instalado. [Baixe o .Net 4.5 Framework aqui.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Você precisará do recurso Experiência Desktop habilitado no Windows.
    
- Você precisará do Microsoft Visual C++ 2013 (x64) instalado. [Baixe o Visual C++ 2013 aqui](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Você precisará do Skype for Business Server 2015 implantado com êxito.
    
## <a name="configuration-requirements"></a>Requisitos de configuração
<a name="ConfigReqs"> </a>

Você precisará dessas configurações adicionais para executar a Ferramenta de Stress and Performance com êxito:
  
- Você precisa fazer logoff no servidor como membro do grupo domínio ou administrador local.
    
- Não é possível instalar a ferramenta de Criação de Usuário (UserProvisioningTool.exe) do Skype for Business Server 2015 em nenhum servidor Front End ou Standard Edition em que as contas de usuário residam.
    
- Quando a ferramenta De criação de usuário é executado várias vezes, cada usuário habilitado para Comunicações Unificadas da Microsoft precisa ter um número de telefone exclusivo.
    
- O tamanho do arquivo de página deve ser gerenciado pelo sistema ou precisa ser pelo menos 1,5 vezes a quantidade de RAM no sistema do computador.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalando a Ferramenta de Stress and Performance do Skype for Business Server 2015
<a name="Installing"> </a>

A instalação não poderia ser mais simples. Você precisa executar o arquivo do Windows Installer, **CapacityPlanningTool.msi**, em cada computador cliente que você usará para simular o tráfego do usuário e em um Servidor front-end em cada pool onde você criará usuários e contatos.
  
Para baixar o .msi, juntamente com os scripts de exemplo mencionados em nossos outros artigos, acesse o link do Centro de Download: [Skype for Business Server 2015,](https://www.microsoft.com/download/details.aspx?id=50367)Ferramenta de Stress and Performance.
  

