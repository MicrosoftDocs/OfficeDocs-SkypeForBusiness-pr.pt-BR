---
title: Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'No Skype para Business Server 2015, ferramentas de gerenciamento são implementadas usando o Windows PowerShell. Windows PowerShell inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. Skype para as ferramentas de Business Server 2015 que são implementadas usando o Windows PowerShell incluem o seguinte:'
ms.openlocfilehash: 25631ce7acf59567b431d7eebdf190c4b63d7913
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="windows-powershell-and-skype-for-business-server-2015-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server 2015
 
No Skype para Business Server 2015, ferramentas de gerenciamento são implementadas usando o Windows PowerShell. Windows PowerShell inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. Skype para as ferramentas de Business Server 2015 que são implementadas usando o Windows PowerShell incluem o seguinte: 
  
- **Construtor de topologia**. Use o construtor de topologias para criar, ajustar e publicar sua topologia planejada e ele valida sua topologia antes de começar a instalações de servidor. Quando você instala o Skype para Business Server 2015 em servidores individuais, os servidores leem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor como prescreve a topologia. Depois da instalação, as informações de configuração são automaticamente replicadas para todos os servidores. Só é possível adicionar componentes à sua implantação usando o Construtor de Topologias.
    
- **Skype do Shell de gerenciamento do servidor de negócios**. Você pode usar Skype do Shell de gerenciamento do servidor de Business para gerenciamento completo da linha de comando da sua implantação.
    
- **Skype para painel de controle do servidor de negócios**. Você pode usar o Skype para interface de usuário do painel de controle do Business Server para gerenciar as tarefas mais comuns em sua implantação.
    
Essas ferramentas usam cmdlets do Windows PowerShell para o gerenciamento da sua implantação, incluindo perto 550 cmdlets de produtos específicos. Os cmdlets de segurança incluídos no Skype para Business Server 2015 são usados principalmente para gerenciar autenticação e os direitos e permissões. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, um número de cmdlets permitem que você use o novo recurso de controle de acesso baseado em função (RBAC) para delegar controle administrativo do Skype para Business Server 2015. Para obter detalhes sobre o Skype para cmdlets Business Server, consulte [Skype do Shell de gerenciamento do Business Server 2015](../../manage/management-shell.md).
  
Os recursos de segurança de script para Windows PowerShell foram projetados especificamente para ajudar a prevenir alguns problemas de segurança relacionados a scripts de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript). Os recursos de segurança do Windows PowerShell estão foi projetados para criar um ambiente no qual os usuários não podem facilmente ou inconscientemente executar scripts. Por padrão, os recursos de segurança do Windows PowerShell estão habilitados. Você pode modificar o estado desses recursos para atender às suas necessidades de script e cumprir vários objetivos de segurança. Isso não quer dizer que o shell impossibilite os usuários de executar scripts. Em vez disso, o shell dificulta, por padrão, que os usuários executem scripts sem perceber. Para obter detalhes, consulte [Segurança de Script do Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

