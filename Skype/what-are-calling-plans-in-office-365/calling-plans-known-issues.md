---
title: "Chamar problemas conhecidos de planos"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# Chamar problemas conhecidos de planos

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Um novo recurso encontrado no Skype for Business Online são os planos de chamada no Office 365. Estes são os problemas atuais que estão sendo controladas e investigação ativamente. Eles serão potencialmente resolvidos quando o recurso for atualizado em compilações futuras no Office 365 e Skype for Business Online.
  
## Chamar problemas conhecidos de planos

|**Problema conhecido**|**Comentários**|
|:-----|:-----|
|Fazer a transição do programa Technical Preview licenças para licenças de produção para planos de chamar automaticamente não atualizar a licença.  <br/> |Adquira suas novas licenças primeiro para que eles estão prontos para serem atribuídos a seus usuários. Remover a licença promocional (Tech Preview) de um usuário e **imediatamente** atribuir o novo **Domésticas chamando planejar** e/ou **Internacional chamando planejar** licenças para o usuário. <br/> Se você estiver removendo e adição de licenças para vários usuários, é muito importante que você remove as licenças de todos os usuários usando o Windows PowerShell e atribua as licenças para todos os usuários também usando o Windows PowerShell **imediatamente**. Isso garante que não há nenhuma interrupção do serviço quando lidar com grandes volumes de atribuições de licença de usuário. Para exemplos de scripts do PowerShell, consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> > [!NOTE]> Se você estiver usando a conectividade de PSTN locais para usuários de implantação híbrida, você  *só*  precisa atribuir uma licença de **Sistema telefônico**. Você **não** deve também atribuir uma plano de chamada de voz.> No entanto, se você estiver ativando chamando planos no Office 365 para usuários que estão no Office 365, você precisa ainda atribuir uma licença **Domésticas chamando planejar** e/ou **Internacional chamando planejar** para esses usuários. Consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).           |
   
## Tópicos Relacionados

[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)
  
[Áudio período discar complementar de conferência](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

