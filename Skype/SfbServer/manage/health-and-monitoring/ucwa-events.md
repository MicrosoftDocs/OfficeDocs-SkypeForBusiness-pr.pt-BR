---
title: Eventos do UCWA no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumo: Aprenda sobre as comunicações unificadas Web API (UCWA) no Skype para Business Server.'
ms.openlocfilehash: f675c16903301412c0c78981b0c17bb9bcc7b24b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897986"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos do UCWA no Skype para Business Server
 
**Resumo:** Saiba mais sobre a Web de comunicação unificada API (UCWA) no Skype para Business Server.
  
Skype para Business Server usa a API de Web de comunicações unificadas (UCWA) para um número de objetivos de acessar o Microsoft Exchange para pesquisas de contatos para a atualização de presença para clientes móveis.
  
A UCWA gravará registros de comportamento operacional como tipos de evento Informacional, Aviso e Erro. A tabela a seguir descreve tais eventos que podem ser gravados com componentes da UCWA.
  
|**ID do evento**|**Tipo de evento**|**Resumo**|**Causa e resolução**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inicializado  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Erro  <br/> |A UCWA encontrou uma exceção inesperada durante a inicialização  <br/> |Ocorreu um erro inesperado durante a inicialização  <br/> Examine os detalhes da exceção na entrada de log do evento associado para determinar a possível causa  <br/> |
|20003  <br/> |Erro  <br/> |A UCWA encontrou uma exceção não manipulada  <br/> |Ocorreu uma exceção não manipulada  <br/> Reinicie o servidor. Se o problema persistir, entre em contato com o suporte do produto  <br/> |
|20004  <br/> |Erro  <br/> |Não é possível acessar o Exchange para foto HD  <br/> |A conexão com o Exchange não está disponível  <br/> Certifique-se de que a conexão com o Exchange está disponível  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperação de uma falha ao acessar o Exchange para foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Erro  <br/> |Não é possível acessar o Exchange para pesquisa de contato  <br/> |A conexão com o Exchange não está disponível  <br/> Certifique-se de que a conexão com o Exchange está disponível  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperação de uma falha em pesquisar contato no Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Aviso  <br/> |Tente assinar mais de uma assinatura de presença permitida por aplicativo  <br/> |Tente assinar mais de uma assinatura de presença permitida por aplicativo  <br/> Verifique se os clientes possuem assinaturas desnecessárias  <br/> |
|20009  <br/> |Aviso  <br/> |Tente assinar mais de uma assinatura de presença permitida por lote  <br/> |Tente assinar mais de uma assinatura de presença permitida por lote  <br/> Verifique se os clientes possuem assinaturas desnecessárias  <br/> |
|20010  <br/> |Erro  <br/> |Não é possível recuperar os dados inband  <br/> |Não é possível recuperar os dados inband  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
|20011  <br/> |Erro  <br/> |Não é possível assinar a presença  <br/> |Não é possível assinar a presença  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
|20012  <br/> |Erro  <br/> |Falha ao registrar o ponto de extremidade  <br/> |Falha ao registrar o ponto de extremidade  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
|20013  <br/> |Erro  <br/> |A MCU de IM não está disponível  <br/> |A MCU de IM não está disponível  <br/> Consulte se a MCU de IM está sendo executada  <br/> |
|20014  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de IM  <br/> |N/D  <br/> |
|20015  <br/> |Erro  <br/> |A MCU de AV não está disponível  <br/> |A MCU de AV não está disponível  <br/> Consulte se a MCU de AV está sendo executada  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de AV  <br/> |N/D  <br/> |
|20017  <br/> |Erro  <br/> |A MCU de AS não está disponível  <br/> |A MCU de AS não está disponível  <br/> Consulte se a MCU de AS está sendo executada  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de AS  <br/> |N/D  <br/> |
|20019  <br/> |Erro  <br/> |A MCU de Dados não está disponível  <br/> |A MCU de Dados não está disponível  <br/> Consulte se a MCU de Dados está sendo executada  <br/> |
|20020  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de dados  <br/> |N/D  <br/> |
|20021  <br/> |Erro  <br/> |Não é possível participar da MCU de IM  <br/> |Não é possível participar da MCU de IM  <br/> Consulte se a MCU de IM está sendo executada  <br/> |
|20022  <br/> |Erro  <br/> |Não é possível participar da MCU de AV  <br/> |Não é possível participar da MCU de AV  <br/> Consulte se a MCU de AV está sendo executada  <br/> |
|20023  <br/> |Erro  <br/> |Não é possível participar da MCU de AS  <br/> |Não é possível participar da MCU de AS  <br/> Consulte se a MCU de AS está sendo executada  <br/> |
|20024  <br/> |Erro  <br/> |Não é possível participar da MCU de Dados  <br/> |Não é possível participar da MCU de Dados  <br/> Consulte se a MCU de Dados está sendo executada  <br/> |
|20025  <br/> |Erro  <br/> |Não é possível acessar o diretório ativo para foto  <br/> |A conexão com o diretório ativo não está disponível  <br/> Certifique-se de que a conexão com o diretório ativo está disponível  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperação de falha ao acessar o diretório ativo para foto  <br/> |N/D  <br/> |
|20027  <br/> |Aviso  <br/> |Não é possível desserializar  <br/> |Não é possível desserializar  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
   

