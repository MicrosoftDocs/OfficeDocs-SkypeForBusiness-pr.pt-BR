---
title: Considerações sobre a junção de domínio do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar um computador de dispositivo do Sistema de Sala do Skype no seu domínio.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093565"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Considerações sobre a junção de domínio do Sistema de Sala do Skype
 
Leia este tópico para saber como ingressar um computador de dispositivo do Sistema de Sala do Skype no seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de associação de domínio

Você pode ingressar o computador de dispositivo do Sistema de Sala do Skype no domínio do Active Directory ou deixá-lo em um Grupo de Trabalho. Considere os seguintes pontos antes de tomar essa decisão:
  
- A junção de domínio ao computador de dispositivo do Sistema de Sala do Skype ajuda a importar automaticamente a cadeia de certificados raiz privada da sua organização.
    
- A junção de domínio ao computador de dispositivo do Sistema de Sala do Skype permite conceder direitos administrativos a usuários e grupos de domínios. Ao fazer isso, não será preciso lembrar a senha da conta de administrador de nível de máquina local.
    
- Ao ingressar em um computador de dispositivo do Sistema de Sala do Skype no domínio, é necessário criar uma Unidade Organizacional (UO) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) para a UO onde todos os objetos de máquina do Sistema de Sala do Skype residem. Ao fazer isso, crie objetos de máquina na UO antes de ingressar o computador de dispositivo do Sistema de Sala do Skype no domínio.
    
- Muitas organizações têm os seguintes GPOs, que afetam as funções de computador do dispositivo do Sistema de Sala do Skype. Verifique se você substitui ou bloqueia a herança desses GPOs na UO do Sistema de Sala do Skype: 
    
  - Tempo de tempo de sessões de logon (bloqueio automático)
    
  - Políticas relacionadas ao gerenciamento de energia
    
  - Exigindo etapas adicionais de autenticação
    
  - Negando o acesso a unidades locais
    
  - Solicitando aos usuários conexões de rede lentas
    
  - Iniciar um determinado programa no logon
    
  - Crie outra conta de usuário de domínio em todos os máquinas ingressas no domínio.
    
  - Push Windows Update to Skype Room System
    
- Como alternativa, você pode optar por deixar o computador do dispositivo no grupo de trabalho. Assim como no cliente do Skype for Business da área de trabalho, isso exige que você importe manualmente a cadeia de certificados raiz no computador de dispositivo do Sistema de Sala do Skype. Você não é obrigado a importar a cadeia de certificados raiz se sua implantação do Skype for Business estiver usando um certificado público (por exemplo, Confiando, VeriSign e assim por diante). 
    
Se você planeja ingressar máquinas do Sistema de Sala do Skype no domínio, para evitar ingressar a máquina do Sistema de Sala do Skype inadvertidamente em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na OU correta. Você pode usar o seguinte cmdlet da máquina do Sistema de Sala do Skype para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar estes cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas que podem causar problemas em um nível mais alto. Uma configuração de Política de Grupo sem Substituição supera uma UO com uma configuração de Herança de Política de Bloqueio. Para obter mais informações, consulte o artigo [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte seus especialistas do Active Directory para garantir que você tenha uma OU que tenha configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existem. É aconselhável habilitar a QoS (Qualidade do Serviço) para dispositivos do Sistema de Sala do Skype.

## <a name="see-also"></a>Confira também
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a qualidade do serviço](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)