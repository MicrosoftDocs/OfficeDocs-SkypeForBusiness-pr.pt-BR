---
title: Windows PowerShell e ferramentas Skype for Business Server de gerenciamento
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'No Skype for Business Server, as ferramentas de gerenciamento são implementadas usando Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa. Skype for Business Server ferramentas implementadas usando Windows PowerShell incluem o seguinte:'
---

# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell e ferramentas Skype for Business Server de gerenciamento
 
No Skype for Business Server, as ferramentas de gerenciamento são implementadas usando Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos ao produto e uma linguagem de script completa. Skype for Business Server ferramentas implementadas usando Windows PowerShell incluem o seguinte: 
  
- **Construtor de Topologias**. Você usa o Construtor de Topologias para criar, ajustar e publicar sua topologia planejada e ela valida sua topologia antes de começar as instalações do servidor. Quando você instala Skype for Business Server servidores individuais, os servidores leem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor conforme direcionado na topologia. Após a configuração, as informações de configuração são automaticamente replicadas para todos os servidores. Os componentes só podem ser adicionados à sua implantação usando o Construtor de Topologias.
    
- **Skype for Business Server Shell de Gerenciamento**. Você pode usar Skype for Business Server Shell de Gerenciamento para gerenciamento completo de linha de comando da sua implantação.
    
- **Skype for Business Server Painel de Controle**. Você pode usar a interface do usuário Skype for Business Server Painel de Controle para gerenciar as tarefas mais comuns em sua implantação.
    
Essas ferramentas usam os cmdlets do Windows PowerShell para gerenciamento de sua implantação, incluindo aproximadamente 550 cmdlets específicos ao produto. Os cmdlets de segurança incluídos no Skype for Business Server são usados principalmente para gerenciar autenticação e direitos e permissões do usuário. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, vários cmdlets permitem que você use o novo recurso Role-Based Controle de Acesso (RBAC) para delegar o controle administrativo de Skype for Business Server. Para obter detalhes sobre os Skype for Business Server cmdlets, [consulte Skype for Business Server Shell de Gerenciamento](../../manage/management-shell.md).
  
Os recursos de segurança de script para Windows PowerShell são projetados especificamente para ajudar a impedir alguns dos problemas de segurança relacionados a script de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript). Os recursos de segurança do Windows PowerShell têm como objetivo a criação de um ambiente no qual os usuários não podem executar facilmente ou sem intenção. Por padrão, os recursos de segurança do Windows PowerShell estão habilitados. É possível modificar o estado desses recursos a fim de acomodar suas necessidades de script e diversas metas de segurança. Isso sem mencionar que o shell impossibilita a execução de scripts pelos usuários. Em vez disso, o dificulta—por padrão—a execução sem intenção de scripts pelos usuários. Para obter detalhes, [consulte Windows PowerShell Segurança de Script](/previous-versions/msdn10/gg261722(v=msdn.10)).
