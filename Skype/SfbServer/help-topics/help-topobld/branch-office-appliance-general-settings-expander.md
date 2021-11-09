---
title: Expansor de Configurações Gerais de Aparelho de Filial
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para editar as configurações para um Aparelho de Filial Persistente ou um Servidor de Borda Persistente, veja as seções a seguir:'
ms.openlocfilehash: e5e75965698f8dbbb97098ccadb0a76c5a3babe9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840093"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expansor de Configurações Gerais de Aparelho de Filial

Para editar as configurações para um Aparelho de Filial Persistente ou um Servidor de Borda Persistente, veja as seções a seguir:

- Configurações gerais

- Configurações de resiliência

- Configurações de Servidor de Mediação



Para um Aparelho de Filial Persistente ou Servidor de Filial Persistente, você encontrará:

## <a name="general-settings"></a>Configurações gerais

O FQDN (nome de domínio totalmente qualificado) do Aparelho de Filial Persistente ou Servidor de Filial Persistente. Edite o FQDN do servidor para alterar o valor. Você deve ter um registro de hospedeiro (A) DNS (Domain Name System) coincidente com o novo valor.

Você pode escolher  **Usar todos os endereços IP configurados** ou  **Limitar uso do serviço aos endereços IP selecionados**. Caso escolha  **Limitar uso do serviço aos endereços IP selecionados**, você definirá o endereço IP primário que o servidor utilizará para todas as comunicações, exceto para o gateway PSTN (rede telefônica pública comutada). Você define um endereço IP separado para utilização de PSTN.

In **Associations**, you can edit or specify the following:

- Associar o Servidor de Arquivamento permite que você selecione associar um Servidor de Arquivamento ao Aparelho de Filial Desavivável ou Servidor de Filial Desavivável. Você pode selecionar em um Servidor de Arquivamento já definido selecionando o servidor na listada ou clique em **Novo** para especificar um novo Servidor de Arquivamento.

    > [!IMPORTANT]
    > O servidor especificado por você deve existir e fazer parte do domínio antes de a publicação da nova topologia recentemente definida.

- Associar o Servidor de Monitoramento permite que você selecione associar um Servidor de Monitoramento ao Aparelho de Filial Desavivável ou Ao Servidor de Filial Desavivável. Você pode selecionar em um Servidor de Monitoramento já definido selecionando o servidor na listada ou clique em **Novo** para especificar um novo Servidor de Monitoramento.

- Associar pool de Borda permite que você selecione associar um Servidor de Borda ou pool ao Aparelho de Filial Desavivável ou Servidor de Filial Suportável. Você pode selecionar a partir de um pool ou Servidor de Borda já definido, selecionando o servidor a partir da lista suspensa, ou clicar em **Novo** para especificar um novo pool ou Servidor de Borda.

## <a name="resiliency"></a>Resiliência

A resiliência oferece alta disponibilidade para o pool de Registradores. Ao providenciar um Registrador de backup, se o Registrador primário falhar, o Registrador de backup poderá assumir as funções do Registrador com falha, permitindo que usuários se conectem e comuniquem. Talvez ocorra uma redução de funcionalidades para os usuários, dependendo em quais sistemas tenham falhado com o Registrador primário.

Na listada, selecione o pool de front-end Edição Enterprise ou o servidor de front-end Edição Standard que atuará como o Registrador de backup para o Aparelho de Filial Desavivável ou Servidor de Filial Desavivável. Você também pode escolher habilitar os intervalos de tempo de Failover e Fallback. Habilitar as definições de tempo de failover e fallback (especificadas em segundos) permite a detecção automática da falha de um Registrador, enquanto o tempo de fallback permite a determinação automática de que o primário está funcionando novamente e pode assumir o processo de Registrador.

> [!IMPORTANT]
> Tome cuidado, quando definir o intervalo de detecção de falha e de fallback, para não inserir um intervalo que causará com que o failover e fallback ocorram se o Registrador falhar em responder por um curto período de tempo. É possível que o Registrador primário não responda por curtos períodos de tempo, baseado no carregamento do pool ou servidores. Os valores padrão para um Aparelho de FilialVivível ou um Servidor de Filial Desavivável em um site para um pool ou Edição Standard Servidor front-end é de 120 segundos para failover e 240 segundos para fallback.

## <a name="mediation-server"></a>Servidor de Mediação

Para **Servidor de Mediação**, você pode especificar o seguinte:

A caixa de seleção para **Servidor de Mediação Colocado ativado** não está disponível em um Aparelho de Filial Persistente ou Servidor de Filial Persistente pois o Servidor de Mediação está colocado.

Você define a porta de escuta nos servidores de pool para TLS (Transport Layer Security). Por padrão é a porta 5067. Caso escolha **Ativar porta TCP**, você deve definir uma porta TCP para o Servidor de Mediação colocado. Esta é uma definição opcional e você deve consultar os requisitos de seu gateway ou requisitos PSTN para determinar a necessidade disso. Por padrão, o valor da porta TCP é 5068.

Você define gateways PSTN que estão associados ao Servidor de Mediação colocado. Caso já tenha definido gateways, eles estarão disponíveis para associação com o Servidor de Mediação. Caso não tenha definido qualquer gateway, mas estejam disponíveis para definir, você pode selecionar **Novo**. Você também pode remover gateways que já estejam configurados para este Servidor de Mediação, selecionando o gateway e clicando em  **Remover**.

Caso tenha mais de um gateway associado a um Servidor de Mediação, o primeiro gateway associado será o gateway padrão. Caso você deva escolher outro gateway como gateway padrão, selecione o gateway que deseja tornar padrão e clique em **Tornar Padrão**.

## <a name="see-also"></a>Confira também

Para maiores detalhes sobre como definir e configurar as configurações para o Aparelho de Filial Persistente ou Servidor de Filial Persistente, consulte[Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).