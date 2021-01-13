---
title: Eventos UCWA no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumo: saiba mais sobre a Unified Communications Web API (UCWA) no Skype for Business Server.'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816661"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos UCWA no Skype for Business Server
 
**Resumo:** Saiba mais sobre a Unified Communications Web API (UCWA) no Skype for Business Server.
  
O Skype for Business Server usa a UNIFIED Communications Web API (UCWA) para várias finalidades, desde acessar o Microsoft Exchange para pesquisas de contato até atualizar a presença de clientes móveis.
  
O UCWA gravará registros de comportamento operacional como tipos de evento Informacional, Aviso e Erro. A tabela a seguir descreve os eventos que podem ser escritos pelos componentes do UCWA.
  
|**ID do Evento**|**Tipo de evento**|**Resumo**|**Causa e resolução**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informacional  <br/> |UCWA inicializado  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Erro  <br/> |O UCWA encontrou uma exceção inesperada durante a inicialização  <br/> |Ocorreu um erro inesperado durante a inicialização  <br/> Examine os detalhes da exceção na entrada de log de eventos associada para determinar a possível causa  <br/> |
|20003  <br/> |Erro  <br/> |O UCWA encontrou uma exceção não maneada  <br/> |Ocorreu uma exceção sem manuseio  <br/> Reiniciar o servidor. Se o problema persistir, contate o suporte do produto  <br/> |
|20004  <br/> |Erro  <br/> |Não é possível acessar o Exchange para foto HD  <br/> |A conexão com o Exchange não está disponível  <br/> Certifique-se de que a conexão com o Exchange está disponível  <br/> |
|20005  <br/> |Informacional  <br/> |Recuperação de uma falha ao acessar o Exchange para foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Erro  <br/> |Não é possível acessar o Exchange para pesquisa de contatos  <br/> |A conexão com o Exchange não está disponível  <br/> Certifique-se de que a conexão com o Exchange está disponível  <br/> |
|20007  <br/> |Informacional  <br/> |Recuperação de uma falha ao pesquisar contato no Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Aviso  <br/> |Tentar assinar mais do que as assinaturas de presença permitidas por aplicativo  <br/> |Tentar assinar mais do que as assinaturas de presença permitidas por aplicativo  <br/> Verifique se há assinaturas desnecessárias nos clientes  <br/> |
|20009  <br/> |Aviso  <br/> |Tentar assinar mais do que as assinaturas de presença permitidas por lote  <br/> |Tentar assinar mais do que as assinaturas de presença permitidas por lote  <br/> Verifique se há assinaturas desnecessárias nos clientes  <br/> |
|20010  <br/> |Erro  <br/> |Não é possível recuperar dados de inband  <br/> |Não é possível recuperar dados de inband  <br/> Se o problema persistir, contate o suporte do produto  <br/> |
|20011  <br/> |Erro  <br/> |Não é possível inscrever a presença  <br/> |Não é possível inscrever a presença  <br/> Se o problema persistir, contate o suporte do produto  <br/> |
|20012  <br/> |Erro  <br/> |Falha ao registrar o ponto de extremidade  <br/> |Falha ao registrar o ponto de extremidade  <br/> Se o problema persistir, contate o suporte do produto  <br/> |
|20013  <br/> |Erro  <br/> |A MCU de IM não está disponível  <br/> |A MCU de IM não está disponível  <br/> Ver se a MCU de IM está em execução  <br/> |
|20014  <br/> |Informacional  <br/> |Recuperação de uma falha ao conectar-se à MCU de IM  <br/> |N/D  <br/> |
|20015  <br/> |Erro  <br/> |A MCU av não está disponível  <br/> |A MCU av não está disponível  <br/> Ver se a MCU de AV está em execução  <br/> |
|20016  <br/> |Informacional  <br/> |Recuperação de uma falha ao conectar-se ao AV MCU  <br/> |N/D  <br/> |
|20017  <br/> |Erro  <br/> |A MCU as não está disponível  <br/> |A MCU as não está disponível  <br/> Ver se a MCU as está em execução  <br/> |
|20018  <br/> |Informacional  <br/> |Recuperação de uma falha ao conectar-se ao AS MCU  <br/> |N/D  <br/> |
|20019  <br/> |Erro  <br/> |A MCU de dados não está disponível  <br/> |A MCU de dados não está disponível  <br/> Ver se a MCU de Dados está em execução  <br/> |
|20020  <br/> |Informacional  <br/> |Recuperação de uma falha ao se conectar ao DATA MCU  <br/> |N/D  <br/> |
|20021  <br/> |Erro  <br/> |Não é possível ingressar na MCU de IM  <br/> |Não é possível ingressar na MCU de IM  <br/> Ver se a MCU de IM está em execução  <br/> |
|20022  <br/> |Erro  <br/> |Não é possível ingressar na MCU de AV  <br/> |Não é possível ingressar na MCU de AV  <br/> Ver se a MCU de AV está em execução  <br/> |
|20023  <br/> |Erro  <br/> |Não é possível ingressar EM MCU de AS  <br/> |Não é possível ingressar EM MCU de AS  <br/> Ver se a MCU as está em execução  <br/> |
|20024  <br/> |Erro  <br/> |Não é possível ingressar em MCU de dados  <br/> |Não é possível ingressar em MCU de dados  <br/> Ver se a MCU de Dados está em execução  <br/> |
|20025  <br/> |Erro  <br/> |Não é possível acessar o Active Directory para foto  <br/> |A conexão com o Active Directory não está disponível  <br/> Certifique-se de que a conexão com o Active Directory está disponível  <br/> |
|20026  <br/> |Informacional  <br/> |Recuperação de uma falha ao acessar o Active Directory para foto  <br/> |N/D  <br/> |
|20027  <br/> |Aviso  <br/> |Não é possível desterializar  <br/> |Não é possível desterializar  <br/> Se o problema persistir, contate o suporte do produto  <br/> |
   

