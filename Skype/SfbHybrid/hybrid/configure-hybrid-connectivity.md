---
title: Configurar a conectividade híbrida | Implantar Skype for Business Server conexão 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Instruções para implementar a conectividade híbrida entre Skype for Business Server e Teams.
ms.openlocfilehash: ffc1205ca91f81e9b9361e4603318bc1a8fcf76c
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887169"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurar conectividade híbrida entre Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Resumo:** Leia este tópico para saber como configurar a conectividade híbrida entre Skype for Business Server e Teams.  A conectividade híbrida permite que você mova seus usuários locais para Teams e permite que os usuários aproveitem os serviços de nuvem.
  
Antes de executar as etapas deste tópico, você deve ter lido [Plan hybrid connectivity between Skype for Business Server and Teams](plan-hybrid-connectivity.md).
  
A tabela a seguir lista as tarefas necessárias para configurar Skype for Business conectividade híbrida e fornece links para os artigos associados para obter mais informações.
  
|Etapa|Descrição|
|:-----|:-----|
|Crie uma conta de locatário do Microsoft 365.   <br/> |Saiba mais Microsoft 365 em [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para garantir que seu ambiente esteja pronto para Microsoft 365, consulte Os [Requisitos do Sistema](https://products.office.com/office-system-requirements).  <br/> Para obter detalhes sobre como configurar Microsoft 365, consulte [Getting Started with Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicione seu domínio à sua organização Microsoft 365 e verifique a propriedade.  <br/> | Você deve adicionar seu domínio à sua Microsoft 365 e, em seguida, seguir as etapas para validar o domínio com Microsoft 365. Essa validação é para confirmar se você é o proprietário do domínio. <br/> Para adicionar seu domínio à sua Microsoft 365, siga as etapas descritas em [Adicionar um domínio a](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Microsoft 365 . Não deixe de revisar as orientações a seguir sobre as [implicações de DNS para organizações que se tornam híbridas](#dns-implications-for-on-premises-organizations-that-become-hybrid). <br/> |
|Configurar a sincronização do Active Directory.  <br/> |A sincronização do Active Directory garante que o Active Directory local seja continuamente sincronizado com o Microsoft 365 para que você crie versões sincronizadas de cada conta de usuário e grupo.  <br/> <br> **Importante:** Você precisa sincronizar as contas do Active Directory para todos os usuários Skype for Business em sua organização entre suas implantações locais e online, mesmo que os usuários não sejam movidos para Teams. Se você não sincronizar todos os usuários, a comunicação entre usuários locais e online em sua organização pode não funcionar conforme o esperado. Para obter mais informações, [consulte Configure Azure AD Conexão para ambientes híbridos](configure-azure-ad-connect.md).         |
| Configure o Skype for Business híbrido. | Há três etapas básicas: <br><br> 1. Configure seu ambiente local para federar com Microsoft 365. <br> 2. Configure seu ambiente local para confiar Microsoft 365 e habilitar o espaço de endereço SIP compartilhado com Microsoft 365.<br> 3. Habilita o espaço de endereço SIP compartilhado em sua Microsoft 365 organização. <br><br> Além disso, se você tiver Exchange local, talvez você queira configurar o OAuth entre seus ambientes Exchange locais e online. <br> <br>Para obter mais informações, consulte [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
|Mover usuários piloto.  <br/> |Depois de concluir as etapas para preparar e configurar seu ambiente para Teams, você pode começar a mover usuários piloto para sua organização Microsoft 365 online. Para obter mais informações, consulte [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>Implicações de DNS para organizações locais que se tornam híbridas

Por padrão, os locatários são criados como modo TeamsOnly. Os administradores não podem alterar essa configuração. No entanto, as organizações híbridas não devem ser o modo TeamsOnly porque isso quebraria a federação para seus usuários locais. Teams tem um mecanismo integrado para garantir que a configuração do TeamsOnly em todo o locatário não seja aplicada a novos locatários híbridos e também que a configuração do TeamsOnly em todo o locatário seja removida dos *locatários existentes* que se tornam híbridos . Esse mecanismo baseia-se no valor do registro DNS do LyncDiscover para qualquer domínio Microsoft 365 verificado (porque uma implantação Skype for Business Server local terá, na maioria dos casos, esse registro), conforme descrito abaixo.

Quando uma nova assinatura Microsoft 365 é processada pela primeira vez, ocorre o seguinte:
- Se ainda não houver nenhum domínio Microsoft 365, o locatário será criado como modo TeamsOnly. O valor é definido por meio do TeamsUpgradeOverridePolicy, que só pode ser definido pela Microsoft. Se o valor da política for UpgradeToTeams, ele tem precedência sobre qualquer valor do TeamsUpgradePolicy.
- Se houver domínios Microsoft 365 verificados, mas não houver registros dns LyncDiscover públicos detectados ou se algum registro do LyncDiscover detectado apontar para Microsoft 365 (sipfed.online.lync.com, sipfed.online.gov.skypeforbusiness.us etc),o locatário será criado como modo TeamsOnly (por meio do TeamsUpgradeOverridePolicy).
- Se houver pelo menos um domínio verificado Microsoft 365 para o qual um registro LyncDiscover é detectado e esse registro aponta em algum lugar diferente do Microsoft 365, o locatário é criado como modo Ilhas.

Quando um locatário de Microsoft 365 existente é re provisionado (normalmente devido a uma alteração em domínios verificados ou em detalhes de assinatura), ocorre o seguinte:
- Se um registro LyncDiscover for encontrado para um ou mais domínios verificados do Microsoft 365 e esse registro não apontar para Microsoft 365, o modo TeamsOnly em todo o locatário (por meio do TeamsUpgradeOverridePolicy) será removido. O modo de locatário será revertido para o que for especificado no nível de locatário do TeamsUpgradePolicy, que, por padrão, é o modo Ilhas.


Há algumas limitações para esse mecanismo de detecção automática:
- Se sua organização não tiver registros DNS públicos, o modo TeamsOnly não será removido, pois Microsoft 365 não poderá detectar os registros. Se sua organização tiver acesso Skype for Business Server sem entradas DNS públicas, você precisará entrar em contato com o Suporte da Microsoft para fazer com que seu locatário seja rebaixado.
- Se você adicionar/atualizar um registro DNS  público a um domínio que já Microsoft 365 um domínio verificado, essa alteração dns não será detectada e o modo TeamsOnly não será removido. O modo TeamsOnly só será removido se o locatário for re provisionado, o que normalmente acontece quando há uma alteração para Microsoft 365 domínios verificados ou para a assinatura.  
