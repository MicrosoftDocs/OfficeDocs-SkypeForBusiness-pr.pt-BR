---
title: Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'No Skype for Business Server, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa. As ferramentas do Skype for Business Server implementadas usando o Windows PowerShell incluem o seguinte:'
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832151"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server
 
No Skype for Business Server, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa. As ferramentas do Skype for Business Server implementadas usando o Windows PowerShell incluem o seguinte: 
  
- **Construtor de Topologias.** Você usa o Construtor de Topologias para criar, ajustar e publicar sua topologia planejada, e ele valida sua topologia antes de começar as instalações do servidor. Quando você instala o Skype for Business Server em servidores individuais, os servidores leem a topologia publicada como parte do processo de instalação, e o programa de instalação implanta o servidor conforme indicado na topologia. Após a configuração, as informações de configuração são automaticamente replicadas para todos os servidores. Os componentes só podem ser adicionados à sua implantação usando o Construtor de Topologias.
    
- **Shell de Gerenciamento do Skype for Business Server.** Você pode usar o Shell de Gerenciamento do Skype for Business Server para o gerenciamento completo de linha de comando de sua implantação.
    
- **Painel de Controle do Skype for Business Server.** Você pode usar a interface do usuário do Painel de Controle do Skype for Business Server para gerenciar as tarefas mais comuns em sua implantação.
    
Essas ferramentas usam os cmdlets do Windows PowerShell para gerenciamento de sua implantação, incluindo aproximadamente 550 cmdlets específicos ao produto. Os cmdlets de segurança incluídos no Skype for Business Server são usados principalmente para gerenciar a autenticação e direitos e permissões do usuário. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, vários cmdlets permitem que você use o novo recurso RBAC (controle de acesso Role-Based) para delegar o controle administrativo do Skype for Business Server. Para obter detalhes sobre os cmdlets do Skype for Business Server, consulte [o Shell de Gerenciamento do Skype for Business Server.](../../manage/management-shell.md)
  
Os recursos de segurança de script para Windows PowerShell são projetados especificamente para ajudar a impedir alguns dos problemas de segurança relacionados a script de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript). Os recursos de segurança do Windows PowerShell têm como objetivo a criação de um ambiente no qual os usuários não podem executar facilmente ou sem intenção. Por padrão, os recursos de segurança do Windows PowerShell estão habilitados. É possível modificar o estado desses recursos a fim de acomodar suas necessidades de script e diversas metas de segurança. Isso sem mencionar que o shell impossibilita a execução de scripts pelos usuários. Em vez disso, o dificulta—por padrão—a execução sem intenção de scripts pelos usuários. Para obter detalhes, consulte [Windows PowerShell Script Security](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

