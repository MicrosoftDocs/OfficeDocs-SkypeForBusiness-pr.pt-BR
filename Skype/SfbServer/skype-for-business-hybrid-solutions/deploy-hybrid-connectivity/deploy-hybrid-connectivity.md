---
title: Implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Resumo: Leia este tópico para saber como implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online.'
ms.openlocfilehash: 7a63858650990d7c1dc7dbcb168bf3070908c19b
ms.sourcegitcommit: bb4e7dec155dee358bec9d6e586730dae0b8f559
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2018
ms.locfileid: "27371146"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online
 
**Resumo:** Leia este tópico para saber como implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online.
  
Antes de executar as etapas neste tópico, você deve ter lido [Planejar conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Conectividade híbrida entre Skype para Business Server e do Skype para Business Online significa que os usuários de um domínio, por exemplo, contoso.com, são divididos entre usando Skype para Business Server no local e Skype para Business Online. Alguns usuários do domínio são hospedados no local, e outros são hospedados online. 
  
A tabela a seguir lista as etapas necessárias para preparar seu ambiente para uma implantação híbrida com o Skype para Business Online e o Microsoft Office 365. 
  
|**Etapa**|**Descrição**|
|:-----|:-----|
|Crie uma conta de locatário para o Office 365 e habilitar Skype para Business Online  <br/> |Saiba mais sobre o Office 365 e Skype para negócios Online no [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para se certificar de que seu ambiente está pronto para o Office 365, consulte os [Requisitos do Sistema](https://products.office.com/en-US/office-system-requirements).  <br/> Para obter detalhes sobre como configurar o Office 365, consulte [Introdução ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicionar seu domínio ao seu locatário do Office 365 e verifique a propriedade  <br/> | Você precisa adicionar seu domínio ao seu locatário do Office 365 e, então, seguir as etapas para validar o domínio com o Office 365. Isso serve para confirmar que você é o proprietário do domínio. <br/> Para adicionar seu domínio ao locatário do Office 365, siga as etapas descritas em [Adicionar seu domínio ao Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Preparar a sincronização do Active Directory  <br/> |Sincronização do Active Directory mantém seu Active Directory local sincronizado continuamente com o Office 365. Assim, é possível criar versões sincronizadas de cada grupo e conta de usuário e também habilitar a sincronização de lista de endereços global (GAL) do seu ambiente local do Microsoft Exchange Server para o Microsoft Exchange Online. Para obter mais informações, consulte [Ferramentas de integração do diretório](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/>  **Importante** Você precisa sincronizar as contas do AD do Skype todos os usuários corporativos em sua organização entre seu local e implantações online, mesmo se os usuários não são movidos para Skype para negócios Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online na sua organização poderá não funcionar conforme o esperado.           |
|Mover usuários-piloto  <br/> |Após concluir as etapas para preparar e configurar seu ambiente do Skype para Business Online, você pode iniciar mover usuários piloto para seu locatário do Office 365 online. Consulte [mover os usuários no local para Skype para negócios Online](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |

## <a name="related-content"></a>Conteúdo relacionado:

Para obter informações sobre como configurar a conectividade híbrida entre Skype para Business Server e Office 365, consulte [Configure a conectividade de híbrido entre Skype para Business Server e Office 365](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-hybrid-connectivity).
