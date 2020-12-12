---
title: Configurar contas para salas do Microsoft Teams
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
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Leia este tópico para saber mais sobre como configurar contas para salas do Microsoft Teams no Exchange e no Skype for Business.
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662516"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para salas do Microsoft Teams
 
Leia este tópico para saber mais sobre as salas do Microsoft Teams e como elas se integram ao Exchange e ao Skype for Business.
  
Este tópico introduz como criar contas usadas por salas do Microsoft Teams no Microsoft Exchange e no Skype for Business. As instruções de implantação para dispositivos de salas do Microsoft Teams são abordadas em [configurar um console de salas do Microsoft Teams](console.md). É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: o ambiente da sua organização é implantado completamente no Microsoft 365 ou no Office 365. Para obter mais informações, consulte [implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365](with-office-365.md).
    
- Implantação local: sua organização tem servidores que ele controla, em que o Active Directory, o Exchange e o Skype for Business Server são hospedados. Para obter mais informações, consulte [implantar salas do Microsoft Teams com o Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma combinação de serviços, com alguns hospedados localmente e alguns hospedados online por meio do Microsoft 365 ou do Office 365. Com as salas do Microsoft Teams, há suporte para os seguintes cenários híbridos:
    
  - Exchange Online com o Skype for Business Server no local. Para obter mais informações, consulte [implantar salas do Microsoft Teams com o Exchange Online (híbrido)](with-exchange-online.md).
    
  - Exchange no local com o Microsoft Teams ou o Skype for Business online. Para obter mais informações, consulte [implantar salas do Microsoft Teams com o Exchange local (híbrido)](with-exchange-on-premises.md).
    
A configuração do dispositivo depende da configuração que você tem.
  
Salas do Microsoft Teams devem ser atribuídas a uma "conta de dispositivo" no Active Directory, Exchange e Skype for Business. A conta é usada para acessar seu calendário de reunião e estabelecer o Microsoft Teams ou a conectividade do Skype for Business. As pessoas podem reservar essa conta agendando uma reunião com ela. As salas do Microsoft Teams poderão participar dessa reunião e oferecer vários recursos aos participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de dispositivo, nenhum desses recursos funcionará. 
  
Cada conta de dispositivo é exclusiva para um único dispositivo de salas do Microsoft Teams e requer alguma configuração:
  
- A conta do dispositivo deve estar configurada corretamente.
    
- Sua infraestrutura deve ser configurada para permitir que as salas do Microsoft Teams validem a conta do dispositivo e para acessar os serviços apropriados da Microsoft.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação. 

Em ambientes híbridos, a conta usada para salas do Microsoft Teams deve ter a sincronização de senha habilitada na sincronização do Azure Active Directory (AAD) porque a autenticação de salas do Microsoft Teams requer o Microsoft 365 ou a autenticação do Office 365. Ao configurar a conta, certifique-se de que o endereço SIP da conta corresponda ao seu nome de usuário principal (UPN) no AAD. 
  
Você pode pensar em uma conta de dispositivo como a conta do recurso que as pessoas reconhecem como uma sala de conferência ou uma conta do espaço de reunião. Para agendar uma reunião usando essa sala de conferência, convide a conta para essa reunião. Para usar as salas do Microsoft Teams com mais eficiência, faça o mesmo com a conta do dispositivo atribuída a cada uma.
  
Se você já tiver uma conta de caixa de correio de recursos configurada para o espaço de reunião no qual está instalando as salas do Microsoft Teams, é possível alterar essa conta de recurso para uma conta de dispositivo. Depois disso, tudo o que você precisa fazer é adicionar a conta de dispositivo a um dispositivo de salas do Microsoft Teams. Consulte os exemplos de configuração da conta do dispositivo fornecidas abaixo.
  
Com configurações adicionais, o gerenciamento remoto é possível usando o Microsoft Azure monitor, conforme descrito em [planejar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-plan.md), [implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md)e [gerenciar dispositivos de salas do Microsoft Teams com o Azure monitor](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima de uma conta de dispositivo para funcionar com as salas do Microsoft Teams. Sua conta de dispositivo pode exigir configuração adicional.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Caixa de correio do Exchange (Exchange 2013 SP1 ou posterior ou Exchange Online)  <br/> |Habilitar a conta com uma caixa de correio do Exchange dá à conta do dispositivo a funcionalidade de receber e enviar solicitações de email e de reunião e para exibir um calendário de reuniões no dispositivo de salas do Microsoft Teams. A caixa de correio de salas do Microsoft Teams deve ser uma caixa de correio de sala.  <br/> |
|O Skype for Business está habilitado  <br/> |O Skype for Business deve estar habilitado para que você possa usar vários recursos de conferência, como chamadas com vídeo, mensagens instantâneas e compartilhamento de tela. O Skype for Business Online e o Skype for Business Server são compatíveis.  <br/> |
|Habilitado por senha  <br/> |A conta do dispositivo deve ser habilitada com uma senha ou não pode autenticar com o Exchange ou o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Embora as propriedades da configuração básica permitam que a conta de dispositivo seja configurada em um ambiente simples, é possível que o ambiente tenha outras restrições em contas de diretório que devem ser atendidas para que as salas do Microsoft Teams usem com êxito a conta do dispositivo.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Os certificados podem ser necessários para o Exchange e o Skype for Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
   
A maneira mais fácil de configurar contas de dispositivos é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de dispositivo ou validar contas de recursos existentes que você tem para ajudar a transformá-las em contas de dispositivo de salas do Microsoft Teams compatíveis.
  
Se você preferir usar a interface do usuário do Microsoft 365 ou do Office 365 em cmdlets do Windows PowerShell, algumas etapas podem ser executadas manualmente. Consulte [criando uma conta de dispositivo usando o Microsoft 365 ou o Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Confira também

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

