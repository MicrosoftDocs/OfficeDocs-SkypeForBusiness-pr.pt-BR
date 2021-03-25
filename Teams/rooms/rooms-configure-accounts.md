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
description: Leia este tópico para saber mais sobre como configurar contas para salas do Microsoft Teams no Exchange e skype for Business.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117469"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para salas do Microsoft Teams
 
Leia este tópico para saber mais sobre salas do Microsoft Teams e como ele se integra ao Exchange e ao Skype for Business.
  
Este tópico apresenta como criar contas usadas pelas Salas do Microsoft Teams no Microsoft Exchange e skype for Business. As instruções de implantação para dispositivos de Salas do Microsoft Teams são abordadas [em Configure a Microsoft Teams Rooms console](console.md). É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: o ambiente da sua organização é implantado inteiramente no Microsoft 365 ou no Office 365. Para obter mais informações, [consulte Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).
    
- Implantação local: sua organização tem servidores que ela controla, onde o Active Directory, o Exchange e o Skype for Business Server estão hospedados. Para obter mais informações, consulte [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma combinação de serviços, com alguns hospedados no local e alguns hospedados online por meio do Microsoft 365 ou Office 365. Com salas do Microsoft Teams, há suporte para os seguintes cenários híbridos:
    
  - Exchange Online com o Skype for Business Server no local. Para obter mais informações, consulte [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).
    
  - Exchange local com o Microsoft Teams ou Skype for Business Online. Para obter mais informações, [consulte Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).
    
A configuração do dispositivo depende da configuração que você tem.
  
As Salas do Microsoft Teams precisam ter uma "conta de dispositivo" no Active Directory, Exchange e Skype for Business. A conta é usada para acessar seu calendário de reuniões e estabelecer a conectividade do Microsoft Teams ou do Skype for Business. As pessoas podem reservar essa conta agendando uma reunião com ela. As Salas do Microsoft Teams poderão participar dessa reunião e fornecer vários recursos aos participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de dispositivo, nenhum desses recursos funcionará. 
  
Cada conta de dispositivo é exclusiva de um único dispositivo do Microsoft Teams Rooms e exige algumas configurações:
  
- A conta do dispositivo deve ser configurada corretamente.
    
- Sua infraestrutura deve ser configurada para permitir que as Salas do Microsoft Teams validem a conta do dispositivo e para alcançar os serviços da Microsoft apropriados.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação. 

Em ambientes híbridos, a conta usada para salas do Microsoft Teams deve ter a sincronização de senha habilitada na Sincronização do Azure Active Directory (AAD), pois a autenticação de Salas do Microsoft Teams requer autenticação do Microsoft 365 ou do Office 365. Ao configurar a conta, certifique-se de que o endereço SIP da conta corresponde ao seu Nome de Entidade de Usuário (UPN) no AAD. 
  
Você pode pensar em uma conta de dispositivo como a conta de recurso que as pessoas reconhecem como uma conta de sala de conferência ou espaço de reunião. Para agendar uma reunião usando essa sala de conferência, convide a conta para essa reunião. Para usar as Salas do Microsoft Teams com mais eficiência, faça o mesmo com a conta de dispositivo atribuída a cada uma delas.
  
Se você já tiver uma conta de caixa de correio de recurso configurada para o espaço de reunião onde você está instalando salas do Microsoft Teams, você pode alterar essa conta de recurso em uma conta de dispositivo. Depois que isso for feito, basta adicionar a conta de dispositivo a um dispositivo do Microsoft Teams Rooms. Consulte exemplos de configuração de conta de dispositivo fornecidos abaixo.
  
Com configuração adicional, o gerenciamento remoto é possível usando o Microsoft Azure Monitor conforme descrito em Planejar o gerenciamento de Salas do Microsoft Teams com o [Azure Monitor,](azure-monitor-plan.md)Implantar o gerenciamento de Salas do Microsoft Teams com o [Azure Monitor](azure-monitor-deploy.md)e Gerenciar dispositivos de Salas do Microsoft Teams com o [Azure Monitor](azure-monitor-manage.md). 
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para uma conta de dispositivo funcionar com salas do Microsoft Teams. Sua conta de dispositivo pode exigir mais configuração.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Caixa de correio do Exchange (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |Habilenciar a conta com uma caixa de correio do Exchange oferece à conta de dispositivo a capacidade de receber e enviar solicitações de email e reunião e exibir um calendário de reuniões no dispositivo salas do Microsoft Teams. A caixa de correio do Microsoft Teams Rooms deve ser uma caixa de correio de sala.  <br/> |
|O Skype for Business está habilitado  <br/> |O Skype for Business deve estar habilitado para usar vários recursos de conferência, como chamadas de vídeo, mensagens IM e compartilhamento de tela. Tanto o Skype for Business Online quanto o Skype for Business Server são suportados.  <br/> |
|Habilitado por senha  <br/> |A conta de dispositivo deve ser habilitada com uma senha ou não pode ser autenticada com o Exchange ou o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Embora as propriedades da configuração básica permitirão que a conta de dispositivo seja configurada em um ambiente simples, é possível que seu ambiente tenha outras restrições em contas de diretório que devem ser atendidas para que as Salas do Microsoft Teams usem com êxito a conta de dispositivo.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Certificados podem ser necessários para o Exchange e o Skype for Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
   
A maneira mais fácil de configurar contas de dispositivo é configurá-las usando Windows PowerShell. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de dispositivo ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de dispositivo compatíveis do Microsoft Teams Rooms.
  
Se você preferir usar a interface do usuário do Microsoft 365 ou office 365 em vez de Windows PowerShell cmdlets, algumas etapas podem ser executadas manualmente. Consulte [Criando uma conta de dispositivo usando o Microsoft 365 ou o Office 365](/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Confira também

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)