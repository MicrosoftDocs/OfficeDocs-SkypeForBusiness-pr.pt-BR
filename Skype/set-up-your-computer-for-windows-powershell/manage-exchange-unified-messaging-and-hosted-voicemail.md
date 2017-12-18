---
title: "Gerenciar mensagens unificadas do Exchange e hospedado caixa postal no Skype for Business Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# Gerenciar mensagens unificadas do Exchange e hospedado caixa postal no Skype for Business Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Você pode gerenciar Exchange Unificação de mensagens e caixa postal hospedado no Skype for Business Online usando um conjunto de cmdlets.
  
## Gerenciar as mensagens unificado do Exchange e hospedado caixa postal

Os seguintes cmdlets podem ser usados para gerenciar Exchange Unificação de mensagens (UM) e políticas de caixa postal hospedado:
  
|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [Novo CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [Remover CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Cria e gerencia objetos de contato usados para serviços de atendedor automático e acesso ao assinante, ao Exchange ATENDEDOR é um serviço hospedado.  <br/> Skype for Business Online funciona com Exchange ATENDEDOR para fornecer vários recursos relacionados a voz, incluindo atendedor automático e acesso ao assinante. Atendedor Automático fornece uma maneira para chamadas automaticamente sejam respondidas e encaminhadas para a pessoa correta. Acesso ao assinante permite que os usuários se conectem ao Exchange ATENDEDOR e recuperar emails, mensagens de voz, contatos e informações de calendário.  <br/> Quando Exchange ATENDEDOR é fornecido como um serviço hospedado, objetos de contato usados para os serviços de atendedor automático e acesso ao assinante devem ser criados usando Microsoft PowerShell. Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact**. <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [Conceder-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Gerencia políticas de caixa postal hospedado usadas na organização. Políticas de caixa postal hospedado especificam chamadas não atendidas como são roteados para o serviço UM Exchange. Essas políticas afetam somente os usuários que foram habilitados para Exchange ATENDEDOR hospedado caixa postal.  <br/> Para verificar se um usuário está habilitado para caixa postal hospedado, execute um comando semelhante à seguinte no prompt de PowerShell.  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

