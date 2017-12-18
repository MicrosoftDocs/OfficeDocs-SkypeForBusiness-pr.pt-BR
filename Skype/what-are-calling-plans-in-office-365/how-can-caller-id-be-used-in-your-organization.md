---
title: "Como a identificação de chamadas pode ser usada em sua organização"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "ID do chamador pode ser controlado para chamadas de entrada e saídas para usuários do sistema telefônico usando uma política chamada CallingLineIdentity."
---

# Como a identificação de chamadas pode ser usada em sua organização

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
ID do chamador pode ser controlado para chamadas de entrada e saídas para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.
  
A funcionalidade de ID do chamador está disponível para todos os usuários de sistema telefônico, independentemente de conectividade de PSTN:
  
- Conectividade PSTN Online
    
- Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)
    
- Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)
    
> [!NOTE]
> Esta política não está disponível no Skype for Business 2015 Server. 
  
## Identificação de chamada de saída

Existem três opções disponíveis para a identificação de chamada PSTN de saída:
  
- O número de telefone atribuído ao usuário, que é o padrão.
    
- Um número de telefone que é classificado como um  *serviço*  e o número de *chamada gratuita*  na sua chamada planos no Office 365 telefone número de estoque. Geralmente, ele é atribuído a uma fila de chamada ou atendedor automático organizacional.
    
- Definido como anônimo.
    
No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:
  
- Inventário de número de quaisquer números de telefone são classificados como um  *usuário*  no seu telefone de chamada de planos
    
- Um número de telefone local do Skype for Business Server
    
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).
  
### Controle de usuário final de identificação de chamada de saída

O atributo EnableUserOverride permite aos usuários únicos ou múltiplos alterar sua configuração de ID do chamador como **anônimo**. Isso se aplica somente quando uma política de CallingLineIdentity está configurada com um parâmetro de CallingIDSubstitute de LineURI ou substituir. O valor padrão de EnableUserOverride é falso.
  
Os usuários finais pode definir sua ID de chamador como **anônimo** usando a guia **Encaminhar configurações chamadas** no Skype para o cliente de desktop do Business.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versão** <br/> |**Compatível** <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |Adiada canal lançado em 13 de junho de 2017 - versão 1701 (Build 7766.2092)  <br/> |Sim  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Não  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Não  <br/> |
   
Os usuários finais também podem definir sua configuração de identificação de chamada na página de configurações do usuário em: [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
  
## Identificação de chamada de entrada

O atributo BlockIncomingCallerID permite para bloquear a ID de chamador PSTN para chamadas de entrada. Você pode definir esse atributo, mas não está disponível para os usuários finais na página de configurações do usuário. E é atualmente disponível somente com conectividade de PSTN Online.
  
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)
  
[Áudio período discar complementar de conferência](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

