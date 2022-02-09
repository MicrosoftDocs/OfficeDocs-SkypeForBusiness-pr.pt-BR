---
title: Pré-requisitos e configuração para o Skype para Ferramenta de Desempenho e Estresse de Barramentos
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisitos ou pré-requisitos para a Ferramenta de Desempenho e Skype for Business Server 2015. Como instalar ou configurar a Ferramenta de Estresse e Desempenho.
ms.openlocfilehash: ec7e2b66427d360a9d54c38146289e4d08f9238d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399615"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Pré-requisitos e configuração para o Skype para Ferramenta de Desempenho e Estresse de Barramentos
 
Requisitos ou pré-requisitos para a Ferramenta de Desempenho e Skype for Business Server 2015. Como instalar ou configurar a Ferramenta de Estresse e Desempenho.
  
Temos as seguintes seções de requisitos de configuração de hardware, software e sistema que você precisará estar ciente antes de executar a Ferramenta de Estresse e Desempenho:
  
- [Requisitos de hardware do cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuração](prerequisites-and-setup.md#ConfigReqs)
    
Além disso, também temos uma seção abaixo para Instalar a Ferramenta de [Desempenho e Skype for Business Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware do cliente
<a name="ClientHardwareReqs"> </a>

Ao executar a Ferramenta de Estresse e Desempenho em sua implantação do Skype for Business Server 2015, você precisará, no mínimo, desses requisitos de hardware atendidos para cada 4500 usuários em seu teste:
  
- Adaptador de rede de 1 gigabit
    
- 8 GB de RAM
    
- 2 CPUs dual-core
    
## <a name="client-software-requirements"></a>Requisitos de software cliente
<a name="ClientSoftwareReqs"> </a>

Os sistemas operacionais com suporte para a Ferramenta de Estresse e Desempenho são:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Além disso, os computadores precisam atender aos seguintes requisitos de software:
  
- Você precisará da Estrutura do Microsoft .NET 4.5 instalada. [Baixe a Estrutura do .Net 4.5 aqui.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Você precisará do recurso Experiência da Área de Trabalho habilitado Windows.
    
- Você precisará Microsoft Visual C++ 2013 (x64) instalado. [Baixe Visual C++ 2013 aqui](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Você precisará da implantação Skype for Business Server 2015 com êxito.
    
## <a name="configuration-requirements"></a>Requisitos de configuração
<a name="ConfigReqs"> </a>

Você precisará dessas configurações adicionais feitas para executar a Ferramenta de Estresse e Desempenho com êxito:
  
- Você precisa fazer logoff no servidor como membro do grupo Domínio ou Administrador Local.
    
- Não é possível instalar Skype for Business Server ferramenta de Criação de Usuário (UserProvisioningTool.exe) do UserProvisioningTool.exe em qualquer servidor front-end ou Edição Standard onde as contas de usuário residirão.
    
- Quando a ferramenta Criação do Usuário é executado várias vezes, cada usuário habilitado para o Microsoft Unified Communications precisa ter um número de telefone exclusivo.
    
- O tamanho do arquivo de página deve ser gerenciado por sistemas ou, de outra forma, precisa ser pelo menos 1,5 vezes a quantidade de RAM no sistema do computador.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalando a ferramenta Skype for Business Server desempenho e estresse do 2015
<a name="Installing"> </a>

A instalação não poderia ser mais simples. Você precisa executar o arquivo Windows Installer, **CapacityPlanningTool.msi**, em cada computador cliente que você usará para simular o tráfego do usuário e em um Servidor Front-End em cada pool onde você criará usuários e contatos.
  
Para baixar o .msi, juntamente com os scripts de exemplo mencionados em nossos outros artigos, acesse o link Centro de Download: [Skype for Business Server 2015, Ferramenta de Estresse e Desempenho](https://www.microsoft.com/download/details.aspx?id=50367).
  

