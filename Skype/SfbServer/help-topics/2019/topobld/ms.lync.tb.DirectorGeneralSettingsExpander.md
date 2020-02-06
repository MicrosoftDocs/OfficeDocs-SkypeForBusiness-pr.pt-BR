---
title: Expansor de Configurações Gerais de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as configurações de um director existente, você verá as seguintes seções:'
ms.openlocfilehash: ffdfd169095175346a89eb6d6d001161bec0f465
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793849"
---
# <a name="director-general-settings-expander"></a>Expansor de Configurações Gerais de Diretor
 
Para editar as configurações de um director existente, você verá as seguintes seções:
  
- Configurações gerais
    
- Serviços Web
    

## <a name="general-settings"></a>Configurações gerais

FQDN (nome de domínio totalmente qualificado) do pool do diretor. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host de Sistema de Nomes de Domínio (DNS) que coincida com o novo valor.
  
Em **Associações**, você pode editar ou especificar o seguinte:
  
Compartilhamento de arquivos para uso do pool de diretor. Selecione um compartilhamento de arquivo existente que já foi definido no construtor de topologias ou clique em **novo** para criar uma nova definição de compartilhamento de arquivos.
  
Monitorar a loja do SQL Server.
  
> [!IMPORTANT]
> Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio. Se você criou um novo compartilhamento de arquivos, o compartilhamento de arquivos deve ser criado no servidor que você designar. 
  
## <a name="web-services"></a>Serviços Web

Para editar ou especificar configurações adicionais para os serviços Web no pool de diretor, você modifica ou especifica as configurações nos serviços Web internos e nos serviços Web externos.
  
Para **Serviços Web internos** , você pode especificar o seguinte:
  
> [!CAUTION]
> Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como **pool01.contoso.com**, não será possível usar o **pool01.contoso.com** para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end. Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.
  
Se você selecionar Substituir FQDN, poderá especificar um FQDN diferente para a identidade dos serviços Web internos no pool. Por padrão, a configuração é o nome do pool atual conforme definido para o pool do diretor.
  
Você pode especificar portas de escuta e publicadas para HTTP e HTTPS que a implantação requer. A configuração padrão da porta 80 para HTTP e porta 443 para HTTPS são as configurações mais comuns e normalmente não precisa ser alterada, a menos que você tenha requisitos específicos dentro de sua organização e design de infraestrutura.
  
Para **Serviços Web externos**, você pode especificar o seguinte:
  
Você pode definir o FQDN dos serviços Web externos. O FQDN especificado aqui será normalmente definido pelos seus requisitos de conexão externa, como o proxy reverso.
  
Você pode especificar portas de escuta e publicadas para HTTP e HTTPS que a implantação requer. As configurações padrão da porta 8080 para HTTP e da porta 4443 para HTTPS são definidas inicialmente. Você poderá alterar essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa. As portas publicadas são definidas como padrão de porta 80 para HTTP e porta 443 para HTTPS. Esses valores determinam quais portas o pool do diretor ou o servidor diretor escutará solicitações de entrada. Geralmente, eles não precisam ser alterados, a menos que haja conflito de requisitos de porta no pool. Portas publicadas internas e externas que usam os mesmos valores de porta são esperadas. Isso não é um conflito.
  

