---
title: Considerações de ingresso no domínio do Sistema de Salas do Skype
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: O administrador pode saber mais sobre como ingressar em um PC de utensílios do sistema de sala da Skype em um domínio do Active Directory, juntamente com as considerações para fazer isso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905433"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Considerações de ingresso no domínio do Sistema de Salas do Skype
 
Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de ingresso no Domínio

Você pode participar do PC de utensílios do sistema da sala Skype ao domínio do Active Directory ou deixá-lo em um grupo de trabalho. Considere os seguintes pontos antes da tomada desta decisão:
  
- Domínio-participar do PC Appliance do sistema de sala do Skype ajuda a importar a cadeia de certificados raiz particulares da sua organização automaticamente.
- Domínio-participar do PC Appliance da sala do Skype permite que você conceda direitos administrativos a usuários e grupos de domínio. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.
- Quando você ingressa em um computador com um aparelho de sistema de sala do Skype para o domínio, é necessário criar uma unidade organizacional (OU) separada para que você possa fornecer exclusões do objeto de política de grupo (GPO) à OU em que todos os objetos do computador do sistema de sala do Skype residem. Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador do aparelho de sistema de sala do Skype para o domínio.
- Muitas organizações têm os seguintes GPOs, que afetam as funções do PC Appliance do Skype Room System. Certifique-se de substituir ou bloquear a herança dos GPOs na unidade organizacional do sistema de sala do Skype:

  - Tempo limite de sessões de logon (bloqueio automático)
  - Políticas relacionadas ao gerenciamento de energia
  - Requerendo etapas adicionais de autenticação
  - Negando acesso a unidades locais
  - Avisando usuários para conexões de rede lentas
  - Iniciar um determinado programa no logon
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
  - Envie o Windows Update para o sistema de sala da Skype
    
- Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho. Da mesma forma que com o cliente Microsoft Teams ou Skype for Business da área de trabalho, isso exige que você importe manualmente a cadeia de certificados raiz no PC do aplicativo do sistema de sala do Skype. Você não será obrigado a importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante). 
    
Se você planeja ingressar em máquinas do sistema de sala do Skype no domínio, para evitar a União inadvertida da máquina do sistema de sala do Skype a uma UO não intencional, o que pode não ser gratuito dos GPOs, certifique-se de participar da UO correta. Você pode usar o cmdlet a seguir da máquina do sistema de sala do Skype para ingressar na UO correta e não receber GPOs que possam bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma Unidade Organizacional e bloqueie herança, há algumas políticas que podem causar problemas a um nível superior. A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política. Para obter mais informações, consulte o artigo [não substituir quando comparado à herança da política de bloqueio](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da política de grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte os especialistas em Active Directory para garantir que sejam fornecidas a você as configurações de GPO apropriadas ou pelo menos uma Unidade Organizacional na qual as políticas descritas anteriormente não existem. É recomendável habilitar a QoS (qualidade de serviço) para dispositivos do sistema de sala do Skype.

## <a name="related-topics"></a>Tópicos relacionados
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a Qualidade de Serviço](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
