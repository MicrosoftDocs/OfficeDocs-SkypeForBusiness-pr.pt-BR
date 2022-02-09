---
title: Expansor de Configurações Gerais de Diretor
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para editar as configurações de um Diretor existente, é possível usar as seguintes seções:'
ms.openlocfilehash: 5013edf82c630ed2c2e155dc4558683a735bcc92
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399785"
---
# <a name="director-general-settings-expander"></a>Expansor de Configurações Gerais de Diretor
 
Para editar as configurações de um Diretor existente, é possível usar as seguintes seções:
  
- Configurações gerais
    
- Serviços Web
    


## <a name="general-settings"></a>Configurações gerais

Nome de domínio totalmente qualificado (FQDN) do Diretor. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host DNS (Sistema de Nome de Domínio) que coincida com o novo valor.
  
Em **Associações** você pode editar ou especificar:
  
Compartilhamento de arquivo para o pool de Diretores a ser usado. Selecione um compartilhamento de arquivos existente que já tenha sido definido no Construtor de Topologias ou clique em **Novo** para criar uma nova definição de compartilhamento de arquivos.
  
Monitorando o SQL Server Store.
  
> [!IMPORTANT]
> Antes de publicar a topologia recém-definida, o servidor especificado precisa existir e fazer parte do domínio. Se você tiver criado um novo compartilhamento de arquivo, ele deverá ter sido no servidor designado por você. 
  
## <a name="web-services"></a>Serviços Web

Para editar ou especificar configurações adicionais para os Serviços Web no pool de Diretores, modifique ou especifique as configurações nos Serviços Web Internos e nos Serviços Web Externos.
  
Para **Serviços Web internos**, é possível especificar o seguinte:
  
> [!CAUTION]
> Se você tiver mais de um pool de Front-End ou Servidor Front-End, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um Servidor Front-End como **pool01.contoso.com**, não poderá usar o **pool01.contoso.com** para outro pool de Front-End ou Servidor Front-End. Se você também estiver implantando Diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deve ser exclusivo de qualquer outro diretor ou pool de diretores, bem como qualquer pool de Front-End ou Servidor Front-End. Se você decidir substituir os serviços Web internos por um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool de Front-End, Diretor ou pool de Diretores.
  
Se você selecionou Substituir FQDN, poderá especificar um FQDN diferente para a identidade dos Serviços Web internos no pool. Por padrão, a configuração é o nome do pool atual, conforme definido para o pool de Diretores.
  
É possível especificar portas de escuta e de publicação para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 80 para HTTP e da porta 443 para HTTPS são as configurações mais comuns e normalmente não precisam ser alteradas, a menos que você tenha requisitos específicos dentro de sua organização e design de infraestrutura.
  
Para **Serviços Web externos**, é possível especificar o seguinte:
  
É possível definir o FQDN dos Serviços Web externos. O FQDN especificado aqui será normalmente definido pelos requisitos de seus requisitos de conexão externa, como o proxy reverso.
  
É possível especificar portas de escuta e de publicação para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 8080 para HTTP e da porta 4443 para HTTPS são definidas inicialmente. Altere essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa. As portas publicadas são definidas por padrão como porta 80 para HTTP e porta 443 para HTTPS. Esses valores determinam quais portas o pool de Diretores ou servidor de Diretor escutará para solicitações de entrada. Normalmente, elas não precisam ser alteradas, a menos que haja conflito de requisitos de porta no pool. Espera-se portas de publicação internas e externas que usam os mesmos valores de porta. Isso não é um conflito.
  

