---
title: Configurar contas para Salas do Microsoft Teams
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
description: Leia este tópico para saber mais sobre como configurar contas para Salas do Microsoft Teams no Exchange e Skype for Business.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117469"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para Salas do Microsoft Teams
 
Leia este tópico para saber mais sobre Salas do Microsoft Teams e como ele se integra com Exchange e Skype for Business.
  
Este tópico apresenta como criar contas usadas pelo Salas do Microsoft Teams no Microsoft Exchange e Skype for Business. As instruções de implantação Salas do Microsoft Teams dispositivos são abordadas em [Configure a Salas do Microsoft Teams console](console.md). É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: o ambiente da sua organização é implantado inteiramente Microsoft 365 ou Office 365. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Microsoft 365 or Office 365](with-office-365.md).
    
- Implantação local: sua organização tem servidores que ela controla, onde o Active Directory, Exchange e Skype for Business Server estão hospedados. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma combinação de serviços, com alguns hospedados no local e alguns hospedados online por meio de Microsoft 365 ou Office 365. Com Salas do Microsoft Teams, há suporte para os seguintes cenários híbridos:
    
  - Exchange Online com Skype for Business Server local. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Exchange Online (Hybrid)](with-exchange-online.md).
    
  - Exchange local com Microsoft Teams ou Skype for Business Online. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Exchange on premises (Hybrid)](with-exchange-on-premises.md).
    
A configuração do dispositivo depende da configuração que você tem.
  
Salas do Microsoft Teams precisa ser atribuída uma "conta de dispositivo" no Active Directory, Exchange e Skype for Business. A conta é usada para acessar seu calendário de reunião e estabelecer Microsoft Teams ou Skype for Business conectividade. As pessoas podem reservar essa conta agendando uma reunião com ela. Salas do Microsoft Teams poderá participar dessa reunião e fornecer vários recursos aos participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de dispositivo, nenhum desses recursos funcionará. 
  
Cada conta de dispositivo é exclusiva de um único dispositivo Salas do Microsoft Teams e exige algumas configurações:
  
- A conta do dispositivo deve ser configurada corretamente.
    
- Sua infraestrutura deve ser configurada para permitir Salas do Microsoft Teams validar a conta do dispositivo e para alcançar a serviços Microsoft.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação. 

Em ambientes híbridos, a conta usada para Salas do Microsoft Teams deve ter a sincronização de senha habilitada na sincronização Azure Active Directory (AAD), pois Salas do Microsoft Teams autenticação requer Microsoft 365 autenticação Microsoft 365 ou Office 365. Ao configurar a conta, certifique-se de que o endereço SIP da conta corresponde ao seu Nome de Entidade de Usuário (UPN) no AAD. 
  
Você pode pensar em uma conta de dispositivo como a conta de recurso que as pessoas reconhecem como uma conta de sala de conferência ou espaço de reunião. Para agendar uma reunião usando essa sala de conferência, convide a conta para essa reunião. Para usar o Salas do Microsoft Teams, faça o mesmo com a conta de dispositivo atribuída a cada uma delas.
  
Se você já tiver uma conta de caixa de correio de recurso configurada para o espaço de reunião onde você está instalando Salas do Microsoft Teams, poderá alterar essa conta de recurso para uma conta de dispositivo. Depois que isso for feito, tudo o que você precisa fazer é adicionar a conta do dispositivo a um Salas do Microsoft Teams dispositivo. Consulte exemplos de configuração de conta de dispositivo fornecidos abaixo.
  
Com configuração adicional, o gerenciamento remoto é possível usando o monitor Microsoft Azure conforme descrito em [Plan Salas do Microsoft Teams management with Azure Monitor,](azure-monitor-plan.md)Deploy Salas do Microsoft Teams management with [Azure Monitor](azure-monitor-deploy.md)e Manage Salas do Microsoft Teams devices with [Azure Monitor](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para uma conta de dispositivo trabalhar com Salas do Microsoft Teams. Sua conta de dispositivo pode exigir mais configuração.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Exchange caixa de correio (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |Habilenciar a conta com uma caixa de correio Exchange oferece à conta do dispositivo a capacidade de receber e enviar solicitações de email e reunião e exibir um calendário de reuniões no dispositivo Salas do Microsoft Teams. A Salas do Microsoft Teams caixa de correio deve ser uma caixa de correio de sala.  <br/> |
|Skype for Business está habilitado  <br/> |Skype for Business deve ser habilitado para usar vários recursos de conferência, como chamadas de vídeo, mensagens IM e compartilhamento de tela. Tanto Skype for Business Online quanto Skype for Business Server são suportados.  <br/> |
|Habilitado por senha  <br/> |A conta de dispositivo deve ser habilitada com uma senha ou não pode ser autenticada com Exchange ou Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Embora as propriedades da configuração básica permitam que a conta de dispositivo seja configurada em um ambiente simples, é possível que seu ambiente tenha outras restrições em contas de diretório que devem ser atendidas para que Salas do Microsoft Teams use com êxito a conta de dispositivo.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Os certificados podem ser necessários para Exchange e Skype for Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
   
A maneira mais fácil de configurar contas de dispositivo é configurá-las usando Windows PowerShell. A Microsoft [forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de dispositivo ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de dispositivos Salas do Microsoft Teams compatíveis.
  
Se você preferir usar o Microsoft 365 ou Office 365 interface do usuário Windows PowerShell cmdlets, algumas etapas podem ser executadas manualmente. Consulte [Criando uma conta de dispositivo usando Microsoft 365 ou Office 365](/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Confira também

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)