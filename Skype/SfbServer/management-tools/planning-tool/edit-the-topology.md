---
title: Editar a topologia no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Após concluir as perguntas iniciais de entrevista, você pode editar o FQDN (nome de domínio totalmente qualificado) e endereços IP do site. Para isso, na página Topologia Global, clique duas vezes no site que deseja editar.
ms.openlocfilehash: 698f7e5e94666a67dd01c55a877a037452fd58e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861188"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Editar a topologia no Skype for Business Server 2015

Após concluir as perguntas iniciais de entrevista, você pode editar o FQDN (nome de domínio totalmente qualificado) e endereços IP do site. Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.

A Ferramenta de Planejamento exibe a topologia do site para o site selecionado. Na parte inferior da página do site, existem quatro guias:

![Topologia do Site da Ferramenta de Planejamento.](../../media/Planning_Tool_Site_Topology.png)

- Topologia do Site - A página exibida atualmente com uma visão geral visual da topologia conforme recomendado.

- Diagrama de Rede de Borda - A página Diagrama de Rede de Borda é onde o designer faz a maior parte do trabalho na Ferramenta de Planejamento. O diagrama exibe a configuração de rede para uma topologia recomendada Skype for Business Server 2015, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga DNS (Sistema de Nomes de Domínio e hardware).

- Relatório de Administrador de Borda - O Relatório de Administração de Borda contém um total de quatro relatórios:

     ![Página Relatório do Administrador de Borda.](../../media/Planning_Tool_Summary_Report.png)

  - Relatório de Resumo - Um relatório geral das configurações da rede de Borda. Se você editar os  valores na página Diagrama de Rede de Borda para os valores de topologia TCP/IP e FQDN que serão usados na implantação real, esses endereços e nomes serão representados aqui. Caso contrário, o texto padrão aparecerá.

  - Relatório de Certificado - O relatório de certificado lista o nome do assunto e os nomes alternativos de assunto para os certificados necessários para a topologia.

  - Relatório de Firewall - O relatório de firewall lista as informações necessárias para configurar firewalls de perímetro na infraestrutura. Isso inclui os endereços IP (valores padrão ou editados), função de servidor, IP de origem e porta, IP de destino e porta, protocolo de transporte, protocolo de aplicativo e anotações relevantes.

  - Relatório DNS - O Relatório DNS lista informações relevantes para as entradas DNS que você deve criar. Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.

- Resumo do Site - O resumo do site apresenta uma visão geral das seleções que você fez respondendo às perguntas iniciais da entrevista ou preenchendo os valores em **Sites de Design.** Informações de capacidade também são apresentadas.

    > [!NOTE]
    > As informações na página do Resumo do site são personalizadas para cada design e podem não conter todas as seções ou informações detalhadas aqui.

## <a name="edit-the-network-configuration-diagram"></a>Editar o diagrama de configuração de rede
<a name="Edit_Network_diagram"> </a>

A maioria do trabalho que um designer faz na Ferramenta de Planejamento do Skype for Business Server 2015 consiste em definir as entradas para os endereços IP e os FQDNs (nomes de domínio totalmente qualificados) para as entradas no diagrama de rede. As informações inseridas nesta página são fornecidas nos relatórios e outras informações contidas na Ferramenta de Planejamento.

![Diagrama de Rede da Ferramenta de Planejamento.](../../media/Planning_Tool_Network_Diagram.png)

A Ferramenta de Planejamento cria um diagrama de rede com texto padrão para endereços IP e FQDNs.

Para editar os valores de entrada e diagrama de rede:

1. Escolha uma seção da rede para começar a trabalhar. Por exemplo, clique duas vezes no texto, **access1.contoso.com**. Na caixa de diálogo aberta, digite o FQDN real do servidor access1.contoso.com e o endereço IP real, substituindo o 131.107.155.3.

2. Clique em **OK** para salvar as entradas.

3. Continue a editar os endereços IP e os FQDNs, fornecendo endereços IP virtuais para balanceadores de carga de hardware ou entradas de servidor para balanceamento de carga do DNS (Sistema de Nome de Domínio) para servidores em pools.

Um recurso útil da Ferramenta de Planejamento é que ela pode atribuir incrementalmente um intervalo de endereços IP e nomes de host do servidor, em vez de exigir que o designer edite cada servidor separado em um pool. Por exemplo:

1. Clique duas vezes nos Servidores Front-End em pool. Quando a caixa de diálogo abrir, selecione **Deseja usar os IPs e o FQDN como pontos de partida para todos os servidores equivalentes neste cluster?**.

2. Por exemplo, o valor inicial do primeiro servidor é fe0101.contoso.com e um endereço IP de 192.168.21.122.

3. Digite fe0.contoso.com no **FQDN** do Servidor front-end , digite 192.168.21.131 no endereço IP do **servidor front-end** e clique em **OK**.

4. O recurso de incremento automático atualiza todos os servidores do pool para fe01 a fe06 e todos os endereços IP de 192.168.21.131 a 136.

Depois de concluir todas as edições, salve a topologia concluindo as seguintes etapas:

Para salvar o design da Ferramenta de Planejamento, clique em **Arquivo** e, em seguida, clique em **Salvar Topologia** ou **Salvar Topologia como**. Se uma caixa de diálogo **Salvar Ferramenta de Planejamento como** for exibida, digite um nome para o arquivo em **Nome do arquivo** e clique em **Salvar**.

## <a name="see-also"></a>Confira também
<a name="Edit_Network_diagram"> </a>

[Editando o design](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)