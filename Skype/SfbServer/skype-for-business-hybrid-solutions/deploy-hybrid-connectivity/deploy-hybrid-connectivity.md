---
title: Implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Resumo: Leia este tópico para saber como implantar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online.'
ms.openlocfilehash: d96cff493daf8efa213c635a5a1454bfa370de9a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online
 
**Resumo:** Leia este tópico para saber como implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online.
  
Antes de executar as etapas neste tópico, você deve ter lido [Planejar conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Conectividade híbrida entre Skype para Business Server e do Skype para Business Online significa que os usuários de um domínio, por exemplo, contoso.com, são divididos entre usando Skype para Business Server no local e Skype para Business Online. Alguns usuários do domínio são hospedados no local, e outros são hospedados online. 
  
A tabela a seguir lista as etapas necessárias para preparar seu ambiente para uma implantação híbrida com o Skype para Business Online e o Microsoft Office 365. 
  
|**Etapa**|**Descrição**|
|:-----|:-----|
|Crie uma conta de locatário para o Office 365 e habilitar Skype para Business Online  <br/> |Saiba mais sobre o Office 365 e Skype para negócios Online no [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para certificar-se de que seu ambiente está pronto para o Office 365, consulte os [Requisitos do sistema](https://go.microsoft.com/fwlink/p/?LinkId=401408).  <br/> Para obter detalhes sobre como configurar o Office 365, consulte [Introdução ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicionar seu domínio ao seu locatário do Office 365 e verifique a propriedade  <br/> | Você precisa adicionar seu domínio ao seu locatário do Office 365 e, então, seguir as etapas para validar o domínio com o Office 365. Isso serve para confirmar que você é o proprietário do domínio. <br/> Para adicionar seu domínio ao seu locatário do Office 365, siga as etapas descritas em [Adicionar seu domínio ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254983).  <br/> |
|Preparar a sincronização do Active Directory  <br/> |Sincronização do Active Directory mantém seu Active Directory local sincronizado continuamente com o Office 365. Assim, é possível criar versões sincronizadas de cada grupo e conta de usuário e também habilitar a sincronização de lista de endereços global (GAL) do seu ambiente local do Microsoft Exchange Server para o Microsoft Exchange Online. Para obter mais informações, consulte [Ferramentas de integração de diretório](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/> > [!IMPORTANT]> Você precisa sincronizar as contas do AD do Skype todos os usuários corporativos em sua organização entre seu local e implantações online, mesmo se os usuários não são movidos para Skype para negócios Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online na sua organização poderá não funcionar conforme o esperado.           |
|Mover usuários-piloto  <br/> |Após concluir as etapas para preparar e configurar seu ambiente do Skype para Business Online, você pode iniciar mover usuários piloto para seu locatário do Office 365 online. Consulte [mover os usuários no local para Skype para negócios Online](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
|Gerenciar usuários em uma implantação híbrida  <br/> |Para obter detalhes sobre como gerenciar usuários em uma implantação híbrida, consulte [Administering usuários em uma implantação híbrida](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx).  <br/> |
   

