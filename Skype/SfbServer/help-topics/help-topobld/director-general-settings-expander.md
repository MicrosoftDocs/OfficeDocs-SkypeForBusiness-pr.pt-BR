---
title: Expansor de configurações gerais de diretor
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para editar as configurações de um diretor existente, são apresentadas as seguintes seções:'
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="director-general-settings-expander"></a>Expansor de configurações gerais de diretor
 
Para editar as configurações de um diretor existente, são apresentadas as seguintes seções:
  
- Configurações gerais
    
- Serviços Web
    
## 

### <a name="general-settings"></a>Configurações gerais

Nome de domínio totalmente qualificado (FQDN) do pool de diretores. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host DNS (Sistema de Nome de Domínio) que coincida com o novo valor.
  
Em **Associações**, você pode editar ou especificar o seguinte:
  
Compartilhamento de arquivo para o pool de diretores a ser usado. Selecione um compartilhamento de arquivo existente que já tenha sido definido no construtor de topologia ou clique em **novo** para criar uma nova definição de compartilhamento de arquivo.
  
Monitorando o armazenamento do SQL Server.
  
> [!IMPORTANT]
> Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio. Se você criou um novo compartilhamento de arquivos, compartilhamento de arquivo deve ser criado no servidor que você designar. 
  
### <a name="web-services"></a>Serviços Web

Para editar ou especificar configurações adicionais para os serviços Web no pool de diretor, modifique ou especifique configurações nos serviços Web internos e serviços Web externos.
  
Internal **serviços da web** , você pode especificar o seguinte:
  
> [!CAUTION]
> Se você tiver mais de um pool de Front-End ou servidor Front-End os serviços Web externos FQDN deve ser exclusivo. Por exemplo, se você definir os serviços Web externos FQDN de um servidor Front-End como **pool01. contoso.com**, você não pode usar **pool01. contoso.com** para outro pool de Front-End ou servidor Front-End. Se você estiver implantando o diretores também, o external FQDN definido para qualquer Diretor de serviços da Web ou pool de diretores deve ser exclusivo de qualquer outro diretor ou diretor do pool, bem como qualquer pool Front-End ou servidor Front-End. Se você decidir substituir os serviços web internos com um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool de Front-End, diretor ou um pool de diretores.
  
Se você selecionar substituir FQDN, você pode especificar um FQDN diferente para a identidade de serviços Web internos no pool. Por padrão, a configuração é o nome do pool atual, conforme definido para o pool de diretor.
  
Você pode especificar as portas de escuta e publicadas para HTTP e HTTPS exigidos para a implantação. A configuração padrão da porta 80 para HTTP e a porta 443 para HTTPS são as configurações mais comuns e geralmente não precisa ser alterado, a menos que você tenha requisitos específicos dentro da organização e design de infraestrutura.
  
Para **serviços web externos**, você pode especificar o seguinte:
  
Você pode definir o FQDN dos serviços Web externos. O FQDN especificado aqui será normalmente definido pelos seus requisitos de conexão externa, como o proxy reverso.
  
Você pode especificar as portas de escuta e publicadas para HTTP e HTTPS exigidos para a implantação. As configurações padrão da porta 8080 para HTTP e a porta 4443 para HTTPS são definidas inicialmente. Você poderá alterar essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa. As portas publicadas estão definidas como padrão da porta 80 para HTTP e a porta 443 para HTTPS. Esses valores determinam quais portas o pool de diretor ou servidor de diretor escutará para solicitações de entrada. Geralmente, essas não precisará ser alterado, a menos que haja em conflito com os requisitos de porta no pool. Espera-se portas publicadas internas e externas que usam os mesmos valores de porta. Isso não é um conflito.
  

