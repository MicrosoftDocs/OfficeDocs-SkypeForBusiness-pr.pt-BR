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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Leia este tópico para saber mais sobre como configurar contas para Salas do Microsoft Teams no Exchange e Skype for Business.
ms.openlocfilehash: 77e1dbe097bbb75697ec52ef7d472df4707ac9cb
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306116"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para Salas do Microsoft Teams
 
Leia este tópico para saber mais sobre Salas do Microsoft Teams e como ele se integra com Exchange e Skype for Business.
  
Este tópico apresenta como criar contas usadas pelo Salas do Microsoft Teams no Microsoft Exchange e Skype for Business. É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: o ambiente da sua organização é implantado inteiramente Microsoft 365 ou Office 365. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Microsoft 365 or Office 365](with-office-365.md).
    
- Implantação local: sua organização tem servidores que ela controla, onde o Active Directory, Exchange e Skype for Business Server estão hospedados. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma combinação de serviços, com alguns hospedados no local e alguns hospedados online por meio de Microsoft 365 ou Office 365. Com Salas do Microsoft Teams, há suporte para os seguintes cenários híbridos:
    
  - Exchange Online com Skype for Business Server local. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Exchange Online (Hybrid)](with-exchange-online.md).
    
  - Exchange local com Microsoft Teams. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Exchange on premises (Hybrid)](with-exchange-on-premises.md).
    
A configuração do dispositivo depende da configuração que você tem.
  
Salas do Microsoft Teams precisa ser atribuída uma "conta de recurso" no Active Directory, Exchange e Skype for Business. A conta é usada para acessar seu calendário de reunião e estabelecer Microsoft Teams ou Skype for Business conectividade. As pessoas podem reservar essa conta agendando uma reunião com ela. Salas do Microsoft Teams poderá participar dessa reunião e fornecer vários recursos aos participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de recurso, nenhum desses recursos funcionará. 
  
Cada conta de recurso é exclusiva de uma única instalação Salas do Microsoft Teams e requer algumas configurações:
  
- A conta de recurso deve ser configurada corretamente.
    
- Sua infraestrutura deve ser configurada para permitir Salas do Microsoft Teams validar a conta de recurso e para alcançar a serviços Microsoft.

> [!NOTE] 
> Se estiver Microsoft Teams painéis, a conta de recurso Salas do Teams entrará nos painéis Salas do Teams e Teams associados.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação.
> 

Em ambientes híbridos, a conta usada para Salas do Microsoft Teams deve ter a sincronização de senha habilitada em Azure Active Directory (AAD) Sincronização porque Salas do Microsoft Teams autenticação requer Microsoft 365 ou Office 365 autenticação. Ao configurar a conta, certifique-se de que o endereço SIP da conta corresponde ao seu Nome de Entidade de Usuário (UPN) no AAD. 
  
Você pode pensar em uma conta de recurso como a conta de recurso que as pessoas reconhecem como uma conta de sala de conferência ou de espaço compartilhado. Quando você deseja agendar uma reunião usando esse espaço, convide a conta para essa reunião.
  
Se você já tiver uma conta de caixa de correio de recurso configurada para o espaço onde você está instalando o Salas do Microsoft Teams, poderá alterar essa conta para uma conta de recurso Salas do Teams usuário. Depois que isso for feito, tudo o que você precisa fazer é entrar Salas do Microsoft Teams com essa conta.
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para uma conta de recurso trabalhar com Salas do Microsoft Teams. Sua conta de recurso pode exigir mais configuração.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Exchange caixa de correio (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |Habilenciar a conta com uma caixa de correio Exchange oferece à conta de recurso a capacidade de receber e enviar solicitações de email e reunião e exibir um calendário de reuniões no dispositivo Salas do Microsoft Teams. A Salas do Microsoft Teams caixa de correio deve ser uma caixa de correio de sala.  <br/> |
|Skype for Business está habilitado  <br/> |Skype for Business pode ser habilitado para usar vários recursos de Skype for Business de conferência, como chamadas de vídeo, mensagens IM e compartilhamento de tela.  <br/> |
|Habilitado por senha  <br/> |A conta de recurso deve ser habilitada com uma senha ou não pode ser autenticada com Microsoft Teams, Exchange ou Skype for Business Server. A expiração de senha deve ser desabilitada em todas as Salas do Teams de recursos.   <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Embora as propriedades da configuração básica permitam que a conta de recurso seja configurada em um ambiente simples, é possível que seu ambiente tenha outras restrições em contas de diretório que devem ser atendidas para que Salas do Microsoft Teams use com êxito a conta de recurso.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Os certificados podem ser necessários para Exchange e Skype for Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
  
## <a name="see-also"></a>Confira também

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
