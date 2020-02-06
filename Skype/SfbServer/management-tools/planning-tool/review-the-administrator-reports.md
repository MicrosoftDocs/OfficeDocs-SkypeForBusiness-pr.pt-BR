---
title: Revisar os relatórios do administrador no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Os Relatórios de Administrador são informações detalhadas para implantações e operações. Os relatórios são gerados com base nas seleções marcadas em Criar Locais. O designer pode adicionar mais valor aos Relatórios de Administrador editando os diagramas de rede e definindo os endereços IP completos e os FQDNs (nome de domínio totalmente qualificado) para servidores, pools e balanceadores de carga.
ms.openlocfilehash: ae6dba3f5967fcd10618a8ab53c754a4f38da748
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816290"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

Os Relatórios de Administrador são informações detalhadas para implantações e operações. Os relatórios são gerados com base nas seleções marcadas em **Criar Locais**. O designer pode adicionar mais valor aos Relatórios de Administrador editando os diagramas de rede e definindo os endereços IP completos e os FQDNs (nome de domínio totalmente qualificado) para servidores, pools e balanceadores de carga.

O recurso Relatórios do administrador permite:

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Analisar o relatório de resumo
<a name="Summary_report"> </a>

O relatório do administrador do Skype for Business é o primeiro dos quatro relatórios valiosos que documentam o design em detalhes. As informações desse relatório, e dos outros três relatórios associados, são úteis para suas Equipes de Tecnologia da Informação:

![Relatório geral de administração de resumo](../../media/General_Summary_Report_Admin_Report.png)

O Relatório de Resumo lista as informações gerais de configuração associadas à sua rede de Borda. O local, o FQDN (nome de domínio totalmente qualificado) e endereço IP, o tipo de rede e os comentários específicos a uma determinada função são documentados.

O designer e cada equipe que for implantar, gerenciar e manter a infraestrutura deve rever o relatório de resumo para obter precisão e garantir que ocorra o mínimo de erros.

Você também pode visualizar relatórios mais detalhados:

- Relatórios de certificados

- Relatório de firewall

- Relatório de DNS

## <a name="review-the-certificates-report"></a>Revisar o relatório de certificados
<a name="Certificates_Report"> </a>

O relatório de certificados contém todos os certificados necessários na implantação do Skype for Business Server 2015 recomendada. A ferramenta de planejamento conta os nomes de assunto e os nomes alternativos de assunto que são inseridos. O texto padrão que é mantido sem edição pode representar um desafio potencial para a equipe responsável pela solicitação e emissão dos certificados. As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido. Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público. Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado.

![Relatório de administradores de certificados](../../media/Certificates_Report_Admin_Report.png)

Leia com atenção e compreenda o uso e a finalidade de cada certificado na implantação. Se houver uma dúvida sobre o que faz um certificado, determine qual servidor ou serviço está se comunicando com o que. Os certificados no Skype for Business Server 2015 são usados para dois objetivos principais:

- MTLS (Mutual Transport Layer Security)-os computadores envolvidos na comunicação cada um apresentam um certificado que comprova sua identidade para outro computador. Isso é conhecido como autenticação de servidor. Não é possível iniciar a comunicação até que cada computador confie na identidade do outro computador.

- Criptografia-criptografia (Secure Sockets Layer, SSL, Transport Layer Security ou TLS) é um meio crítico para ajudar a proteger a comunicação, ajudar a garantir a privacidade e criar um sistema de comunicação e colaboração confiável.

## <a name="review-the-firewall-report"></a>Analisar o relatório de firewall
<a name="Firewall_report"> </a>

O Skype for Business Server 2015 tem um conjunto de regras de firewall potencialmente complexo. A ferramenta de planejamento reduz essa complexidade ao gerar um relatório que define em detalhes todos os requisitos de firewall, com base nos critérios de entrada do designer. O administrador de firewall de TI pode usar esse relatório para configurar e definir as regras necessárias.

Do ponto de vista do gerenciamento de firewall, o relatório deve ser revisado cuidadosamente para garantir que não haja nenhum conflito com as regras de firewall existentes e que não hajam políticas ou procedimentos que possam ser violados.

![Relatório de administração de firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Examinar o relatório de DNS
<a name="DNS_Report"> </a>

O Relatório de DNS que faz parte dos Relatórios do Administrador fornece detalhes sobre todas as entradas recomendadas e conhecidas para o DNS (Sistema de Nomes de Domínio) nas redes de perímetro, internas e externas. Se o designer tiver concluído as edições no diagrama de rede e todos os endereços IP e FQDNs (nomes de domínio totalmente qualificados) estiverem definidos com seus valores de produção, o Relatório de DNS apresentará um excelente recurso de configuração. Este relatório também pode ser usado como um documento para solução de problemas operacionais.

![Relatório de administração de DNS](../../media/DNS_Report_Admin_Report.png)

Você deve ter uma revisão detalhada do Relatório DNS feita por sua equipe de gerenciamento do DNS para garantir que não existam erros que possam causem dificuldade durante a implantação ou compliquem uma sessão de solução de problemas.

## <a name="see-also"></a>Confira também
<a name="DNS_Report"> </a>

[Reviewing the Administrator Reports](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
