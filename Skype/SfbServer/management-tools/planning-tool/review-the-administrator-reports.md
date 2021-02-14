---
title: Revisar os relatórios de administrador no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Os Relatórios de Administrador são informações detalhadas para implantações e operações. Os relatórios são gerados com base nas seleções marcadas em Sites de Design. O designer pode adicionar mais valor aos Relatórios de Administrador editando os diagramas de rede, definindo os endereços IP completos e os FQDNs (nome de domínio totalmente qualificado) para servidores, pools e balanceadores de carga.
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823341"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Revisar os relatórios de administrador no Skype for Business Server 2015

Os Relatórios de Administrador são informações detalhadas para implantações e operações. Os relatórios são gerados com base nas seleções marcadas em **Sites de Design.** O designer pode adicionar mais valor aos Relatórios de Administrador editando os diagramas de rede, definindo os endereços IP completos e os FQDNs (nome de domínio totalmente qualificado) para servidores, pools e balanceadores de carga.

O recurso de relatórios do Administrador permite que você:

- [Revisar o Relatório de Resumo](review-the-administrator-reports.md#Summary_report)

- [Revisar o Relatório de Certificados](review-the-administrator-reports.md#Certificates_Report)

- [Revisar o Relatório de Firewall](review-the-administrator-reports.md#Firewall_report)

- [Analisar o relatório dns](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Revisar o Relatório de Resumo
<a name="Summary_report"> </a>

O Relatório de Administradores do Skype for Business é o primeiro de quatro relatórios valiosos que documentam seu design em detalhes. As informações neste relatório e nos outros três relatórios associados são úteis para suas Equipes de Tecnologia da Informação:

![Relatório geral de administração de resumo](../../media/General_Summary_Report_Admin_Report.png)

O Relatório de Resumo lista as informações gerais de configuração associadas à rede de Borda. O local, o FQDN (nome de domínio totalmente qualificado) e o endereço IP, o tipo de rede e os comentários específicos de uma determinada função são documentados.

O designer e cada uma das equipes que implantará, gerenciará e manterá a infraestrutura deve analisar o relatório resumido para ter certeza de que os erros estão no mínimo.

Você também pode exibir relatórios mais detalhados:

- Relatório de certificados

- Relatório de firewall

- Relatório DNS

## <a name="review-the-certificates-report"></a>Revisar o Relatório de Certificados
<a name="Certificates_Report"> </a>

O Relatório de Certificados contém todos os certificados necessários na implantação recomendada do Skype for Business Server 2015. A Ferramenta de Planejamento é responsável pelos nomes de assunto e nomes alternativos de assunto inseridos. O texto padrão que não é emitido pode representar um desafio potencial para a equipe responsável por solicitar e emitir os certificados. As informações do certificado também incluem informações sobre o local de onde o certificado pode ser normalmente emitido. Se a infraestrutura não tiver uma infraestrutura de chave pública interna (PKI), todos os certificados poderão ser solicitados por meio de um provedor de certificados público. Os campos EKU (Uso Estendido de Chave) e Atribuir a do relatório são muito úteis para ajudar a compreender quais devem ser a finalidade e a localização de cada certificado.

![Relatório de Administração de Certificados](../../media/Certificates_Report_Admin_Report.png)

Revise cuidadosamente e compreenda o uso e a finalidade de cada certificado na implantação. Se houver uma pergunta sobre o que um certificado faz, determine qual servidor ou serviço está se falando com o que. Certificados no Skype for Business Server 2015 são usados para duas finalidades principais:

- Mutual Transport Layer Security (MTLS) - Os computadores envolvidos na comunicação apresentam um certificado que prova sua identidade para outro computador. Isso é conhecido como autenticação de servidor. A comunicação não pode começar até que cada computador confie na identidade do outro computador.

- Criptografia - A criptografia (Secure Sockets Layer, ou SSL, e Transport Layer Security, ou TLS) é um meio essencial para ajudar a proteger as comunicações, ajudar a garantir a privacidade e criar um sistema confiável de comunicação e colaboração.

## <a name="review-the-firewall-report"></a>Revisar o Relatório de Firewall
<a name="Firewall_report"> </a>

O Skype for Business Server 2015 tem um conjunto potencialmente complexo de regras de firewall. A Ferramenta de Planejamento reduz essa complexidade gerando um relatório que define em detalhes todos os requisitos de firewall, com base nos critérios de entrada do designer. O administrador de firewall de TI pode usar esse relatório para configurar e definir as regras necessárias.

Do ponto de vista do gerenciamento de firewall, o relatório deve ser cuidadosamente revisado para garantir que não haja conflitos com as regras de firewall de saída e que não há políticas ou procedimentos que possam ser violados.

![Relatório de Administração do Firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Analisar o relatório dns
<a name="DNS_Report"> </a>

O Relatório DNS, que faz parte do Relatório de Administradores, detalha todas as entradas recomendadas e conhecidas para o DNS (Sistema de Nomes de Domínio) nas redes internas, de perímetro e externas. Se o designer concluiu as edições para o diagrama de rede e todos os endereços IP e FQDNs (nomes de domínio totalmente qualificados) são definidos para seus valores de produção, o Relatório dns fornece um excelente recurso de configuração. Esse relatório também pode servir como um documento de solução de problemas operacionais.

![Relatório de administração de DNS](../../media/DNS_Report_Admin_Report.png)

Você deve fazer com que sua equipe de gerenciamento de DNS revise completamente o Relatório DNS para garantir que não haja erros que possam causar dificuldade durante a implantação ou que possam complicar uma sessão de solução de problemas.

## <a name="see-also"></a>Confira também
<a name="DNS_Report"> </a>

[Analisando os relatórios do administrador](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
