---
title: Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'No Skype for Business Server, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. As ferramentas do Skype for Business Server implementadas usando o Windows PowerShell incluem o seguinte:'
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296879"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server
 
No Skype for Business Server, as ferramentas de gerenciamento são implementadas usando o Windows PowerShell. O Windows PowerShell inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. As ferramentas do Skype for Business Server implementadas usando o Windows PowerShell incluem o seguinte: 
  
- **Construtor**de topologias. Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada e valida sua topologia antes de iniciar instalações de servidor. Quando você instala o Skype for Business Server em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação, e o programa de instalação implanta o servidor conforme direcionado na topologia. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Shell de gerenciamento do Skype for Business Server**. Você pode usar o Shell de gerenciamento do Skype for Business Server para o gerenciamento de linha de comando completo da sua implantação.
    
- **Painel de controle do Skype for Business Server**. Você pode usar a interface do usuário do painel de controle do Skype for Business Server para gerenciar as tarefas mais comuns na sua implantação.
    
Essas ferramentas usam cmdlets do Windows PowerShell para o gerenciamento da sua implantação, incluindo cmdlets próximos a 550 cmdlets específicos do produto. Os cmdlets de segurança incluídos no Skype for Business Server são usados principalmente para gerenciar autenticação e direitos e permissões de usuário. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, vários cmdlets permitem que você use o novo recurso de controle de acesso baseado em função (RBAC) para delegar o controle administrativo do Skype for Business Server. Para obter detalhes sobre os cmdlets do Skype for Business Server, consulte [Shell de gerenciamento do Skype for Business Server](../../manage/management-shell.md).
  
Os recursos de segurança de script para Windows PowerShell foram projetados especificamente para ajudar a prevenir alguns problemas de segurança relacionados a scripts de tecnologias mais antigas, incluindo o Microsoft Visual Basic Scripting Edition (VBScript). Os recursos de segurança do Windows PowerShell destinam-se a criar um ambiente no qual os usuários não podem executar scripts de forma fácil ou desconhecida. Por padrão, os recursos de segurança do Windows PowerShell estão habilitados. Você pode modificar o estado desses recursos para atender às suas necessidades de script e cumprir vários objetivos de segurança. Isso não quer dizer que o shell impossibilite os usuários de executar scripts. Em vez disso, o shell dificulta, por padrão, que os usuários executem scripts sem perceber. Para obter detalhes, consulte [segurança de script do Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

