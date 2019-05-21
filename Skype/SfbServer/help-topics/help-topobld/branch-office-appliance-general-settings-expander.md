---
title: Expansor de Configurações Gerais de Aparelho de Filial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para editar as configurações de um aparelho de ramificação sobreviventes existente ou um servidor de ramificação sobreviventes, você receberá as seguintes seções:'
ms.openlocfilehash: 9a3f88dff701c240d56ee7c095cb289a1ae8a834
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301558"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expansor de Configurações Gerais de Aparelho de Filial

Para editar as configurações de um aparelho de ramificação sobreviventes existente ou um servidor de ramificação sobreviventes, você receberá as seguintes seções:

- Configurações gerais

- Configurações de resiliência

- Configurações do Servidor de Mediação



Para um aparelho de ramificação sobreviventes ou um servidor de filiais sobreviventes, você recebe o seguinte:

## <a name="general-settings"></a>Configurações gerais

O nome de domínio totalmente qualificado (FQDN) do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host DNS (Sistema de Nome de Domínio) que coincida com o novo valor.

Você pode selecionar **Usar todos os endereços IP configurados** ou **Limitar o uso do serviço para os endereços IP selecionados**. Caso escolha **Limitar o uso do serviço para os endereços IP selecionados**, você definirá o endereço IP principal que o servidor utilizará para todas as comunicações, exceto para o gateway PSTN (rede telefônica pública comutada). Você define um endereço IP separado para uso do PSTN.

Em **Associações**, é possível editar ou especificar o seguinte:

- Associar o servidor de arquivamento permite que você selecione para associar um servidor de arquivamento com o aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes. Você pode selecionar em um servidor de arquivamento já definido, selecionando o servidor na lista suspensa ou clicar em **novo** para especificar um novo servidor de arquivamento.

    > [!IMPORTANT]
    > Antes de publicar a topologia recém-definida, o servidor que você especificar já deverá existir e fazer parte do domínio .

- Associar o Monitoring Server permite que você selecione associar um servidor de monitoramento com o aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes. Você pode selecionar em um servidor de monitoramento já definido, selecionando o servidor na lista suspensa ou clicar em **novo** para especificar um novo servidor de monitoramento.

- Associar o pool de bordas permite que você selecione a associação de um servidor de borda ou pool com o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes. Você pode escolher entre um Servidor de Borda ou pool já definido, selecionando o servidor na lista suspensa, ou clicar em **Novo** para especificar um novo Servidor de Borda ou pool.

## <a name="resiliency"></a>Resiliência

A resiliência oferece alta disponibilidade ao pool de Registradores. Ao providenciar um Registrador de backup, se o Registrador principal falhar, o Registrador de backup poderá assumir suas funções e permitir que os usuários se conectem e se comuniquem. Dependendo dos sistemas que falharam com o Registrador principal, os usuários poderão enfrentar uma redução de funcionalidades.

Na lista suspensa, selecione o pool de front-end do Enterprise Edition ou o servidor front-end Standard Edition que atuará como registrador de backup para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes. Você também pode habilitar os intervalos de tempo de Failover e Fallback. Habilitar as configurações de tempo de failover e fallback (especificadas em segundos) permite detectar automaticamente as falhas de um Registrador, enquanto o tempo de fallback permite determinar automaticamente que o principal voltou a funcionar e pode reassumir o processo de Registrador.

> [!IMPORTANT]
> Quando definir o intervalo de detecção de falha e de fallback, cuidado para não inserir um intervalo que provoque o failover e o fallback se o Registrador não responder por um curto período. É possível que o Registrador principal não responda por curtos períodos, baseado no carregamento do pool ou servidores. Os valores padrão para um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes em um site para um pool ou um servidor front-end da edição padrão são 120 segundos para failover e 240 segundos para fallback.

## <a name="mediation-server"></a>Servidor de Mediação

No caso do **Servidor de Mediação**, você pode especificar o seguinte:

A caixa de seleção do **servidor de mediação posicionado habilitada** não está disponível em um aparelho de ramificação sobreviventes ou em um servidor de ramificação sobreviventes porque o servidor de mediação está posicionado.

Você define a porta de escuta nos servidores de pool para o protocolo TLS. Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário. Por padrão, o valor de porta TCP é 5068.

Você define os gateways PSTN associados ao servidor de mediação posicionado. Se você já definiu gateways, eles estarão disponíveis para serem associados ao servidor de mediação. Caso não tenha definido nenhum gateway, mas eles estejam disponíveis para tal, selecione **Novo**. Você também pode remover gateways que já estão configurados para este servidor de mediação. Selecione o gateway e clique em **Remover**.

Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão. Caso precise escolher outro gateway como gateway padrão, selecione o gateway para tornar padrão e clique em **Tornar Padrão**.

## <a name="see-also"></a>Confira também

Para obter detalhes sobre como definir e definir as configurações para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes, consulte [soluções de resiliência de site de filial](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).


