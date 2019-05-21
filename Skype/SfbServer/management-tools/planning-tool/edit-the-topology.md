---
title: Editar a topologia no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Após concluir as perguntas iniciais da entrevista, você poderá editar o nome de domínio totalmente qualificado (FQDN) e o endereço IP do site. Para isso, na página Topologia Global, clique duas vezes no site que deseja editar.
ms.openlocfilehash: 91a7ad51c66d810255fcc3239d25298bd370501f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274286"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Editar a topologia no Skype for Business Server 2015

Após concluir as perguntas iniciais da entrevista, você poderá editar o nome de domínio totalmente qualificado (FQDN) e o endereço IP do site. Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.

A ferramenta de planejamento exibe a topologia de site para o site selecionado. Na parte inferior da página do site, existem quatro guias:

![Topologia do site da ferramenta de planejamento](../../media/Planning_Tool_Site_Topology.png)

- Topologia de site-a página atualmente exibida com uma visão geral da topologia, conforme recomendado.

- Diagrama de rede de borda – a página de diagrama de rede de borda é onde o designer faz a maior parte do trabalho na ferramenta de planejamento. O diagrama exibe a configuração de rede para uma topologia do Skype for Business Server 2015 recomendada, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga de hardware e DNS (Domain Name System).

- Relatório de administração de borda-o relatório de administração de borda contém um total de quatro relatórios:

     ![Página de relatório de administração de borda](../../media/Planning_Tool_Summary_Report.png)

  - Relatório de resumo-um relatório geral de configurações para a configuração de rede de borda. Se você editar os valores na página **Diagrama da rede de borda ** para a topologia TCP/IP e os valores do FQDN que irão ser usados na implantação atual, tais endereços e nomes serão representados aqui. De outro modo, o texto padrão aparecerá.

  - Relatório de certificado-o relatório de certificado listará o nome do assunto e os nomes alternativos do assunto para os certificados necessários para a topologia.

  - Relatório de firewall-o relatório de firewall lista as informações necessárias para configurar firewalls de perímetro na infraestrutura. Isso inclui os endereços IP (seja de valores padrão ou editados), função do servidor, IP e porta de origem, IP e porta de destino, protocolo de transporte, protocolo de aplicativo e notas relevantes.

  - Relatório DNS-o relatório DNS lista informações relevantes para as entradas de DNS que você deve criar. Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.

- Resumo do site – o resumo do site apresenta uma visão geral das seleções que você fez respondendo às perguntas iniciais da entrevista ou preenchendo os valores em **sites de design**. A informação de capacidade também é apresentada.

    > [!NOTE]
    > As informações na página do Resumo do site são personalizadas para cada design e podem não conter todas as seções ou informações detalhadas aqui.

## <a name="edit-the-network-configuration-diagram"></a>Editar o diagrama de configuração de rede
<a name="Edit_Network_diagram"> </a>

A maior parte do trabalho que um designer faz na ferramenta de planejamento do Skype for Business Server 2015 consiste em definir as entradas dos endereços IP e dos FQDNs (nomes de domínio totalmente qualificados) para as entradas no diagrama de rede. As informações inseridas nesta página são fornecidas nos relatórios e outras informações contidas na ferramenta de planejamento.

![Diagrama de rede da ferramenta de planejamento](../../media/Planning_Tool_Network_Diagram.png)

A ferramenta de planejamento cria um diagrama de rede com o texto padrão para endereços IP e FQDNs.

Para editar os valores de entrada e diagrama de rede:

1. Escolha uma seção da rede para começar o trabalho. Por exemplo, clique duas vezes no texto, **rp01.contoso.net **. Na caixa de diálogo que for aberta, digite o FQDN real do servidor access1.contoso.com e o endereço IP real, substituindo o 131.107.155.3.access1.contoso.com.

2. Clique em **OK** para salvar as entradas.

3. Continue a editar os endereços IP e os FQDNs, fornecendo endereços IP virtuais para balanceadores de carga de hardware ou entradas de servidor para balanceamento de carga do DNS (Sistema de Nome de Domínio) para servidores em pools.

Um recurso útil da Ferramenta de Planejamento é que ela pode atribuir incrementalmente um intervalo de endereços IP e nomes de host do servidor, em vez de exigir que o designer edite cada servidor separado em um pool. Por exemplo:

1. Clique duas vezes nos Servidores Front-End em pool. Quando a caixa de diálogo for aberta, selecione **Deseja usar os IPs e o FQDN como pontos de partida para todos os servidores equivalentes neste cluster?**.

2. Por exemplo, o valor inicial para o primeiro servidor é fe0101.contoso.com e um endereço IP de 192.168.21.122.

3. Digite fe0.contoso.com em  **FQDN do Servidor Front-End **, digite 192.168.21.131 em **Endereço IP do Servidor Front-End ** e clique em **OK**.

4. O recurso de incremento automático atualiza todos os servidores no pool para fe01 até fe06 e todos os endereços IP de 192.168.21.131 até 136.

Após ter concluído todas as edições, salve a topologia completando as seguintes etapas:

Para salvar o design da ferramenta de planejamento, clique em **arquivo**e, em seguida, clique em **salvar topologia** ou **salvar topologia como**. Se uma caixa de diálogo **Salvar Ferramenta de Planejamento como** for exibida, digite um nome para o arquivo em **Nome do arquivo** e clique em **Salvar**.

## <a name="see-also"></a>Confira também
<a name="Edit_Network_diagram"> </a>

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
