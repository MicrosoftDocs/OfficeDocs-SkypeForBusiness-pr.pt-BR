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
description: O administrador pode saber mais sobre como ingressar em um pc de dispositivo do Skype Room System em um domínio do Active Directory, juntamente com as considerações para fazê-lo.
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

Você pode ingressar no computador do dispositivo Skype Room System para o domínio do Active Directory ou deixá-lo em um Grupo de Trabalho. Considere os seguintes pontos antes da tomada desta decisão:
  
- A junção de domínios no computador do dispositivo Skype Room System ajuda a importar automaticamente a cadeia de certificado raiz privada da sua organização.
- A junção de domínios no computador do dispositivo Skype Room System permite que você conceda direitos administrativos a usuários de domínios e grupos. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.
- Ao ingressar em um computador móvel do Sistema de Salas do Skype com o domínio, é necessário criar uma Unidade Organizacional (OU) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) para a UO onde residem todos os objetos de máquina do Sistema de Salas do Skype. Quando você fizer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do Sistema de Sala do Skype ao domínio.
- Muitas organizações têm os seguintes GPOs, que afetam as funções do computador do dispositivo Skype Room System. Verifique se você substitui ou bloqueia a herança desses GPOs no Skype Room System OU:

  - Tempo limite de sessões de logon (bloqueio automático)
  - Políticas relacionadas ao gerenciamento de energia
  - Requerendo etapas adicionais de autenticação
  - Negando acesso a unidades locais
  - Avisando usuários para conexões de rede lentas
  - Iniciar um determinado programa no logon
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
  - Push Windows Update to Skype Room System
    
- Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho. Assim como no cliente da área de trabalho do Microsoft Teams ou do Skype for Business, isso exige que você importe manualmente a cadeia de certificado raiz no computador do dispositivo Skype Room System. Você não será obrigado a importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Confie, VeriSign e assim por diante). 
    
Se você planeja ingressar em máquinas do Sistema de Sala do Skype para o domínio, para evitar ingressar inadvertidamente em uma OU não intencional, que pode não ser gratuita de GPOs, certifique-se de ingressar na O ou correta. Você pode usar o seguinte cmdlet do computador Skype Room System para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma Unidade Organizacional e bloqueie herança, há algumas políticas que podem causar problemas a um nível superior. A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política. Para obter mais informações, consulte o artigo Sem Substituição em Comparação com a Herança [de Política de](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) Bloqueio na documentação da Política de Grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte os especialistas em Active Directory para garantir que sejam fornecidas a você as configurações de GPO apropriadas ou pelo menos uma Unidade Organizacional na qual as políticas descritas anteriormente não existem. É aconselhável habilitar a QoS (Qualidade de Serviço) para dispositivos do Skype Room System.

## <a name="related-topics"></a>Tópicos relacionados
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a Qualidade de Serviço](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
