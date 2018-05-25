---
title: Expansor de Configurações Gerais de Aparelho de Filial
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para editar as configurações para um aparelho de filial persistente ou o servidor de filial persistente existente, são apresentadas as seguintes seções:'
ms.openlocfilehash: 1f0c1b47d0ea042f29172f4557ef78db42f83216
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expansor de Configurações Gerais de Aparelho de Filial
 
Para editar as configurações para um aparelho de filial persistente ou o servidor de filial persistente existente, são apresentadas as seguintes seções:
  
- Configurações gerais
    
- Configurações de resiliência
    
- Configurações do Servidor de Mediação
    
## 

Para um aparelho de filial persistente ou servidor de filial persistente, são apresentadas com os seguintes itens:
  
### <a name="general-settings"></a>Configurações gerais

O nome de domínio totalmente qualificado (FQDN) do aparelho de filial persistente ou servidor de filial persistente. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host DNS (Sistema de Nome de Domínio) que coincida com o novo valor.
  
Você pode selecionar **Usar todos os endereços IP configurados** ou **Limitar o uso do serviço para os endereços IP selecionados**. Caso escolha **Limitar o uso do serviço para os endereços IP selecionados**, você definirá o endereço IP principal que o servidor utilizará para todas as comunicações, exceto para o gateway PSTN (rede telefônica pública comutada). Você define um endereço IP separado para uso do PSTN.
  
Em **Associações**, é possível editar ou especificar o seguinte:
  
- Associe o servidor de arquivamento permite que você selecione essa opção para associar um servidor de arquivamento com o aparelho de filial persistente ou servidor de filial persistente. Você pode selecionar a partir de um servidor de arquivamento já definido, selecionando o servidor da lista suspensa ou clique em **novo** para especificar um novo servidor de arquivamento.
    
    > [!IMPORTANT]
    > Antes de publicar a topologia recém-definida, o servidor que você especificar já deverá existir e fazer parte do domínio . 
  
- Associar Monitoring Server permite que você selecione essa opção para associar um Monitoring Server com o aparelho de filial persistente ou servidor de filial persistente. Você pode selecionar de um servidor de monitoramento já definido selecionando o servidor na lista suspensa, ou clique em **novo** para especificar um novo Monitoring Server.
    
- Associe pool permite que você selecione essa opção para associar um pool ou servidor de borda com o aparelho de filial persistente ou servidor de filial persistente de borda. Você pode escolher entre um Servidor de Borda ou pool já definido, selecionando o servidor na lista suspensa, ou clicar em **Novo** para especificar um novo Servidor de Borda ou pool.
    
### <a name="resiliency"></a>Resiliência

A resiliência oferece alta disponibilidade ao pool de Registradores. Ao providenciar um Registrador de backup, se o Registrador principal falhar, o Registrador de backup poderá assumir suas funções e permitir que os usuários se conectem e se comuniquem. Dependendo dos sistemas que falharam com o Registrador principal, os usuários poderão enfrentar uma redução de funcionalidades.
  
Na lista suspensa, selecione o pool de Front End do Enterprise Edition ou Standard Edition servidor Front-End que atuará como o registrador de backup para o aparelho de filial persistente ou servidor de filial persistente. Você também pode habilitar os intervalos de tempo de Failover e Fallback. Habilitar as configurações de tempo de failover e fallback (especificadas em segundos) permite detectar automaticamente as falhas de um Registrador, enquanto o tempo de fallback permite determinar automaticamente que o principal voltou a funcionar e pode reassumir o processo de Registrador.
  
> [!IMPORTANT]
> Quando definir o intervalo de detecção de falha e de fallback, cuidado para não inserir um intervalo que provoque o failover e o fallback se o Registrador não responder por um curto período. É possível que o Registrador principal não responda por curtos períodos, baseado no carregamento do pool ou servidores. Os valores padrão para um aparelho de filial persistente ou um servidor de filial persistente em um site para um pool ou servidor Standard Edition Front End é 120 segundos para failover e 240 segundos para fallback. 
  
### <a name="mediation-server"></a>Servidor de Mediação

No caso do **Servidor de Mediação**, você pode especificar o seguinte:
  
A caixa de seleção **servidor de mediação colocado ativado** não está disponível em um aparelho de filial persistente ou servidor de filial persistente pois o servidor de mediação está colocado.
  
Você define a porta de escuta nos servidores de pool para o protocolo TLS. Por padrão, essa porta é a 5067. Se você selecionar **Habilitar porta TCP**, será necessário definir uma porta TCP para o Servidor de Mediação colocado. Essa é uma configuração opcional, e você deverá verificar seus requisitos de gateway ou PSTN a fim de determinar se isso é necessário. Por padrão, o valor da porta TCP é 5068.
  
Você define os gateways PSTN associados com o servidor de mediação colocado. Se você já tenha definido gateways, eles estarão disponíveis para associar o servidor de mediação. Caso não tenha definido nenhum gateway, mas eles estejam disponíveis para tal, selecione **Novo**. Você também pode remover os gateways que já estiverem configurados para o servidor de mediação. Selecione o gateway e clique em **Remover**.
  
Se você tiver mais de um gateway associado a um servidor de mediação, o primeiro gateway associado será o gateway padrão. Caso precise escolher outro gateway como gateway padrão, selecione o gateway para tornar padrão e clique em **Tornar Padrão**.
  
### 

Para obter detalhes sobre como definir e configurar as definições para o aparelho de filial persistente ou servidor de filial persistente, consulte [Branch-Site Resiliency Solutions](http://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).
  

