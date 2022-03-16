---
title: Configurar contas para Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: Leia este tópico para saber mais sobre como configurar contas para Salas do Microsoft Teams (incluindo Surface Hub) e telefones de área comum.
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514726"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para Salas do Microsoft Teams
 
Este tópico apresenta como criar contas usadas por Salas do Microsoft Teams. É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: o ambiente da sua organização é implantado inteiramente Microsoft 365 ou Office 365.
    
- Implantação local: sua organização tem servidores que ela controla, onde o Active Directory, Exchange e Skype for Business Server estão hospedados. Para obter mais informações, [consulte Deploy Salas do Microsoft Teams with Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma combinação de serviços, com alguns hospedados no local e alguns hospedados online por meio de Microsoft 365 ou Office 365. Com Salas do Microsoft Teams, os seguintes cenários híbridos são suportados:
    
  - Exchange Online com Skype for Business Server local.
    
  - Exchange local com Microsoft Teams.
    
A configuração do dispositivo depende da configuração que você tem.
  
Salas do Microsoft Teams precisa ter uma "conta de recurso" no Active Directory, Exchange e (se necessário) Skype for Business. A conta é usada para acessar o calendário da reunião e estabelecer Microsoft Teams e/ou Skype for Business conectividade. As pessoas podem reservar essa conta agendando uma reunião com ela. Salas do Microsoft Teams poderá participar dessa reunião e fornecer vários recursos aos participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de recurso, nenhum desses recursos funcionará.
  
Cada conta de recurso é exclusiva de uma única Salas do Microsoft Teams instalação.
  
- A conta de recurso deve ser configurada corretamente.
    
- Sua infraestrutura deve ser configurada para permitir Salas do Microsoft Teams validar a conta de recurso e alcançar a serviços Microsoft.

> [!NOTE] 
> Se estiver Microsoft Teams painéis, a conta de recurso Salas do Teams entrará nos painéis Salas do Teams e Teams associados.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação.
> 
Em ambientes híbridos que não estão usando Skype for Business, é altamente recomendável criar a conta na Azure Active Directory. Se a conta deve ser criada usando o Active Directory local, a sincronização de senha deve ser habilitada em Azure Active Directory (AAD) Conexão sincronização porque Salas do Microsoft Teams autenticação requer Microsoft 365 ou Office 365 autenticação. Ao configurar a conta, certifique-se de que o endereço de email da conta corresponde ao nome principal do usuário (UPN) no AAD. 
  
Você pode pensar em uma conta de recurso como a conta que as pessoas reconhecem como o nome de uma sala de conferência ou de espaço compartilhado. Quando você deseja agendar uma reunião usando esse espaço, convide a conta de recurso para essa reunião.
  
Se você já tiver uma Exchange de caixa de correio de recurso configurada para o espaço onde você está instalando o Salas do Microsoft Teams, poderá alterar essa conta para uma conta de recurso Salas do Teams de usuário. Depois que isso for feito, tudo o que você precisa fazer é entrar Salas do Microsoft Teams com essa conta.
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para uma conta de recurso trabalhar com Salas do Microsoft Teams. Sua conta de recurso pode exigir mais configuração.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Exchange caixa de correio (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |A Exchange de correio oferece à conta de recurso a capacidade de receber e enviar solicitações de email e reunião e exibir um calendário de reunião no Salas do Microsoft Teams. A Salas do Microsoft Teams caixa de correio deve ser uma caixa de correio de recurso do tipo "room".  <br/> |
|Skype for Business está habilitado  <br/> |Skype for Business pode ser habilitado para usar vários recursos Skype for Business de conferência, como chamadas de vídeo, mensagens de IM e compartilhamento de tela.  <br/> |
|Habilitado por senha  <br/> |A conta de recurso deve ser habilitada com uma senha ou não pode ser autenticada com Microsoft Teams, Exchange ou Skype for Business Server. A expiração de senha deve ser desabilitada em todas as Salas do Teams de recursos.   <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Embora as propriedades para a configuração básica permitirão que a conta de recurso seja configurada em um ambiente simples, é possível que seu ambiente tenha outras restrições sobre contas que devem ser atendidas para que Salas do Microsoft Teams use com êxito a conta de recurso.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Os certificados podem ser necessários para Exchange e Skype for Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |

## <a name="see-also"></a>Confira também

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
