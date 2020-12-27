<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#"
      ><img
        height="30px"
        src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAApQAAAFKCAMAAACUzT/MAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAL9UExUReA5NPW7veA6Nd8pL+A4S++VmN4hJ94iKP///+A5P94jKeAwNf/+/vvm6f76+uRKT+E5PuVRVvzq6+AuNP739+A5QOA6NP75+eAsMuEzOf309Ot5ffzs7fzp6eAyN94kKudhZv3v8Pzu7+E1O/3y8/719uA4TPzs7P3w8eNBRvfKzfOuseA5M++Ulvre3/319eI/ROyBhv/9/frb3P3x8vjP0d8lK++Ul/zt7t8sMeI6QPvi4/nZ2vGhpPCbnvbGx/vk5d8mLP77+/KqrPS0tt8wL+RMUe6OkfbDxeZWW+lqbt8qLN8tLeRITeZZXvvj5eNGS+t7f/W7vOI+Q+p1efW9vut3e/vm5+pwdOdgZOhiZultcd8qMOlobOZYXPGgovW+wPrh4uhkaOdeYuI8Qd8nLedjcvKsrf78/PfNzuNDSO6Lje+SlfKoquVUWeI9QvnW1+2Hi/CZnPS3ueRLUO2Hiupvc+dbYPjO0OA2MuZhcPrf4POsruZdbONESelscPjR0vnV1vnY2e6MkOE3PO2Eh+AzMfKmqPbCwuyAg+2Gifrd3uA6OPna2/fIyfCcn+VTV/bAwffLzOhmauA7QfjT1PKlp/fJy/GjpuZebu+ZluRHTORTZOx9geA6O98oK/Oxs/bExupzduddYfjQ0fXAwfOtr+A5Q/bCxO6Pkux/guhna/Owsupzd+VWZ+FBR+A4RuA4SPvo6OVaavjS1PCanfS2t/W6u+pydvvo6vS4u+2JjfnU1ednduJDP/OztOVOU+hpd/GfoeE+UehsevCanONJROZXW+E4PfCdoOE/Ou+XmuVPVOJHTeROSep1gudjX+ZcWOVYaOJEVvjU1+p2c/SzteNJWuE8N+ZcYfvk5uROXvGhqvCfnfKutuyCfu2LiO6Sj+t9euhsae2Ml+t8iedldOA6TeVYU+lwbPW9w+yCju+XoeRUUPGjoPKqp+RRTfCcpu6Rm/OyuulvffGkrvre3fvo6+yHhPOysOhpZeRPVPKpsvvn5/jQzjAt3CUAACCGSURBVHja7Z19XBXXmcdHxM69XEpEr+FN3gIGKAF5F1RAXqpCFxQVBEEFlIqKAorRLdZ3C2pFRI22xtb3+BJjSpVYNWptTeJL0qRNsonb1223m6abvmy329267mfhisK9c2bmnDNz75058/z+hOHhzJ3vPXOec37nOZzJ/br6yrMvTjOBQP3i3N+Ek+ef9fQEKkHagTJw+yjPPr14Hx4GSBtQblpg/s6zQCVIQ1BeP29+6RGTQCVIE1Bar5jNozyfCKgEuR3K5DCz2fwdT6ASpBkoL7/dy+Srzw6C0vMVoBLkRiitU3qRNL/kaS+gEuQ+KFv39DFp9/IGKkFuhXLIUzYm7V/ej6icDQ8FoHSDfBpsSA7MBgGVIDdDOanwEZOjPJECKgFKl+tEyyMmUS9voBLkBijr7/YjiX552/RjoBKgdKFmlz9mcpSnuH78eXgyAKWrNPXBYyYf+zBEqPwePBqA0iVK2rX3CZOvSjEJVAKULlLwuSdICpZygEqQO6Ds8h1gUvrlbdN3gUqA0tnK3DuIyVdlmQQqAUpna3TZICQlZoPsqPwbPB+A0nlas3wwk0IfhgiVI+ABAZTOUluCHZOvPusJVILcCmV4iR2SmC9voBKgdJ42FNszOcqTQEAlQOkE5dm/unFmgwbrq0AlQKmyIhMdkCR5eQOVAKUTtPFjRyZHeZLqq6PhMQGU6in2vCOThC9voBKgVFeBqwRI4s8GAZUApRO0qULI5EueVAIqAUpVlL9OyCTNyxuoBChVUl+ZIJVe3jZ9A6gEKBUqPgzF5EvUTAKVAKVS2coEmZXPBtlRmQ5PC6Cklt9ps1ndlzdQCVAqU81ZNJMvKWMSqAQoqVXagmZylKdifQWoBCgplDvOLKLvPKsClc/AEwMoSTWpUozJV1VgEqgEKMnVPlmMyVGe6gioBCiJlLTCLKoFf/0uUAlyOZTd5eJMzrxq8vv0+0AlyLVQdjwQZ9J823ZJ6r/+QAUqvwxUApRY8r69V4LJs/X9l7X+xz+pQGU4PDeAUl4jzkkgaV7XOnDl6J++AlSCXADlF5ZLMWk+aXex9fJvFVMZDU8OoJRW5l5JJmcJIf7RD6CvBDkRymfKJJE0twQj/ij5N8oGl9+APY4ApbjWFEgzaS4VGYb+9EUlVMLOW4BSVG0JMkxuFf3TsX/5MlAJUh3K6G0ySJqXS+Uk3h0/+jd6KsGLDlAidKFYjsm9XTIhJl75CVAJUg/KReflmDQ3yEeZ/ecXgUqQOlAKywQhfBhWnEiBP/8GUAlSAcpNH8szmdCEGaz+yH9S+S1hjyNAOUiH5V/dZnMmQcD3f/8ToBKkAMqxqzCQNBcmEQW9/+//DLvJQLRQJofhMLmuhniG6X+/ClSCqKDsmY7DpPkwRWifT38IVAKUxLIuxULSHETZpAukVmDYeWt4KOP34DE5OYq6UTWEVmDYIWFwKNFlghA6oaRZz/z1x0AlQIk55GvARNK8SmHD/Ia8DlQClDjv1UJcJgsClbdtMcHgEqg0KpQnWnCZ3LtGldbtwLcCA5WGhDJ3mBlbd9VqH74VGKg0IJTiZYKECvNRr4XY+8xgP7jhoJz6AJ/J8zvVbeQX8KzAsJvMWFAmXRyFz6S5TfVm7vwNjlsDdt4aCcrgcgIkzZXeTmjo93CswEClcaDc70vC5Nv3ndPUsX/5ClAJUPZr/l4SJs09TmtsUrbs4BKoNASUUbOIkDQfcmp7Za3AQKUBoOxaTsbkA2dbduSswEAl81AemEnGpPmI89uc8nNJK/CXU+CxsgxlegkhkubNLml17qdS+8yASpahPD6PlMniMa5q+Pu/F3dr/BaoZBbKZQmkTO7d4MKm14gPLoFKRqGULxMkVJZrGx/+v2JHTrwOVLII5fvF5EzW5rq6+aJHTgCVDEIZe56cyfM73HEHIkdOvB4JD5ctKAO3mimU56Z7QB85AVSyBeXEBTRMXnLfXYz+6ytAJdtQXl9Hw+Tb3e68D+vl14FKdqG0NpupdNndtyI8cuL7QCUbUCbX0jG5TQM3s8PRCvz9QHjCDEDZ8zYdk77RmridvznsMwMq9Q+ldQodkuZRHVq5Iav9kRNApd6hjD9LyaT5tIZuyf7ICaBS31AOeZuWyY+t2rqrTYOOnAAqdQwlfpkgYWnz9zV3X5//8xO3xg+BSr1COaGQmknzfC3eWeTPvwJU6hvKUy30TJ6t1+a91U/ttwL/cCw8aP1BWX+XHkm7I+a1pn4rMFCpPyhnVypg0hyr6RucZrMCE1MZvjP7eua4hqWnG+JuLnuta2e6Cm+D+qiNp2JvxjVsPt2w4kB+R7LiKjOBrV0rX7jbcHpzw7jMw9kT3Vm1JrApf1zJ2WLfe/fuFYcdvZLZ3uqjDMrsB0qYnKX1711KnxWYgMqUrouVLRYvfrC8RsasTsxrop9kmD1kc9gSf/uYlqK549opi3BbN2SeuxeQZhfQUlQ4LFs1Mr2tKcEjgoNH9Co4fOwgCU2zE7MqtvAOykmYO38iNZRJWXuVMNmigxOOc3uPnMDcTTatbU8EL6qFhctqKP5/U1xnlVjIkcW3iMuBBcdWjheLFxKWWaP08wrffzOo+OBbIf6PZQkYpDj7i7tv+nqJtMWrKC6eCsoR58yKVKqPYUrqj16XryZj7ZkzlJdRTnEbWecWfPuGTMjQgjaC/s1nSOFI6Xh1x2JFv4Ebwxw0y3FcMiKvNkAyvJ3L4cIs6cbUFXZRQNmpjMmtuhk9v/+pzGaNlKwYHkshJU3Y/3VTiQUn5Jals/HiRd9ehxNv/BSReB2OV1rs9592nZNtb9nA1fsKMdpSu48YyrdGKWFyuZ62wkgWg/O7OZ7HVuh6vG2bO4+m4Ya0NGN0wJHDhuPGG5n4EBVhg+N1AdGDflu6GiNy5eOrow6F4n1a26IJofRQwuTeL7AyC3GqhSeSV7n8aCkqsY4kZMRNuQw/r5EknmUcIi+bKLhq4Luw5hhW3Nr+yz/E/oLwCWSDPO65ryuAMo4RJK3beGL5x8lMepwcThrSN1Uq3oV5pPHWCVlodbxm6OOhdmCiF17U1Y8uLyNqSjPJ2bEc99y3qF/gFVY2mNxxg6fRZKkjMGbvoYiYdlp0iJHUkEMRMMjxxdnqSF5a/9JH13TcmJ19lycTvln4Y1EkUHLccEoqEzaxwWRHAE+nnFuiMYdE0IVcLTJHMK2YLt4Sh+R3tmB6Idn28wP4yD/Ve/l+8o+MYOGvD0qOsqM8wAaT1VU8tSpFdgE1UEccvh855I2gjZeTaQ+l4GZtKVszQcSYJFN2BkVLFu4kgfK5r1N1leuTmGCySwGTvd3GBNQQtVxBxDrEidRtoQoCJkpD2deVBhF9bUz7M6ga0lhD0lNSDSunT2OCyWkBSpjkQxBQRq5WFJLPdAwYpyzeej8pKNtNplVkPV62hbIh69IJoKQaVl5ngslcX0XPOwexXpGuLGSvHOqEnVYab46fBJQzTLvIomVYqBtyrJ4ESvLZyiAmmDRtVrlT650r6eQV6wV1xqcIKoVQ7u7gXadVJFASDysfjGaCyU3iSefQ4UUFqysWrC44OFx01In4ZuYuUOPhJQ8EzJQfhQ6VHXKu9xaFcvtwVXDLGH6w17Y2fbi/9GW7CaDsHVaSeYXa2ego54iM5SszuyY9noT1ts5OXbvtHsKq0eknjDhLar1tSe32+YdnZLevXHTr0IKZ4ijtGnjNDZEaPBQdzXotNblmUnLTqbbEAgtGtiOE0ks5kDOPtq3p9uvj3tsveGPsNok5zPHRBFASJjvNbDC5AYnO3GrUpp5peRUOC9kRk4RXrRDvSmrz4u2GVD7JeWfR/cqygYuSxU048zIdZv6iLj8v3k8dEINSqaounRKsoWxsFu1+S0igJJqtnMfIVizUUtmCq6KXJzcPTtVDsxHz8GK9X+Mw5Kx49+0lwi/FyYHfjykS6yTPIb03DxvEJhPqFhNBWRWRMDNhvEXWT5J2CD3PEz1OpN/2WkMCJcGwUqUj5t2usYgpaemyClFxIQPvWOGvwxeKTBytEC21ZT3g4E4KzZf51vRprqh5LmqrCEgJKbhQLinLS509xsfHxxrd2nFzstSlyy+IflQTzqL/pICop8Sn8i4bTJqOCD+y7XJ/E1zSPwhDleO8hH4Oz0uaJaPt3CBDZwz61Wsi3e5KyTGJyJTUOSwoLSVd9vM2WRIXL5Wc4rmJ/nqcIIESe1ip5hHzbpVwArAIo2r7ftsrdTLicJZq9JtwkVzE9oEOtmpwBhmNHpkVyngbfLajESqVh3LkUkGV0WHir265LYO7ka/wTm8SKHuHlThUnk9mhElTreADO4n11u9dlQtB2AusSOf6Qgw/cPdju4XFrlDYISQLDfLxYpFGzsZAOSjXIwaIolCmrZRtxxpk4nWECMrnsObQl7HCpLcgi/DH3AV3MwPlWr2LegJ4q7F+6x+NPe0WiK6isiYvrI9/KnJ1erM0lBnIovWiUL6M0Y4ToRIuYcyeEmdYWe7NCpRWwb7QFtw/RdmwokJQU3iYe2/qK/vmmDba/Qw5DY+5yx7p46maJAVlI3ovjRiUU7DacRE1EVBDBCXGsNJZR8y7QeGCIU+FknBLUWM0bMtp/Rx+vH1KnY2cVseNV43qo8pMD0WhFOvSRaCch9k3ob5ZcWRQylszVjLDJKLXqFWCOKqj7MH/+5RCh7F6MeXUs8TyZN390WJQJoh1Nmgoq3ATixpEl12URAilhzuPmHetRoykmEMjelGdURCvC7UBw48gAGp+amugCJTiXToaSvzTihEeJ68mQiilN5I9eIYhKFMEfVsI/Y5hH0TqHaOkrhZiS3Ud0f6TyATELP5VkWVL8S4dCeUW/A8qBbFCMYwQSulhZTZDTJpyG6kySpE8U2RikFaThtLmFgPTn6iucguu3UkSSpJtrIiuch4plFLDys0mpiRc+oihXtSvRKyiK2nbOEQmT3qY+lxhjAjkzOHCFDIo/YMVDd35kenEUHq4/4h51wixlaaWcrVKmMnzXscVNC2pSNI8hKdk3PocUvNMKCjLiZqBWAQ/RQyl2GzlzH1sMWm6ifi8i+lqlq1EeP+VNG2j0OaY4KfGtw6lliRCKHcTtSKfdFWKQ1KJHlbuYoxJ0wWkI2FYOkWoc8JAQ5Q0DbFX7BZ5lKt4uyDzTWRQvkX2xowSDhnmkEOJpnJPLmtQ5qLLrEUkEr8ScoWZ7kw/JU0rEC4CBqsSBjVF6UcIZSVhK94Ujt1zyaFEDSvPx5uY0xSx59S5i+xud4aSm+AIO5e5NHGW4UApndQP4xXPUQjXuobep4ASMaxcxB6TyHmXx3OC87Ka8Ff51woDdClp2FRhvMM0cYIxPL2hmwihzJlA2IoZwn+6nwJKIZXnTCwqUfJxFSVWY27aPCPcIaWo+JdwQqgqmCoQRl2Eg96EUMbUEzaiVfgeWUsDpeOw8qluJqEMl6vRYyluyMYAU7hOXaioXeuFGw/oAt2Vh1JmPV0IZRhpI6zDydJvUSh7h5WDqRxiYlP5GGMuy/Lmammzt59wbeimklZ5t1Bu4xeoS9kkJRLKEuJW+JIsIUlBafcCTzSxKszan5bVKzaKv7W6h5INmuQUGEE2bSPxKpCvsXKBFMoG4lYUkhl9OSkqn9Qn6IxmFkorfuWfdYkdIjMZ+4Tp5UMljZqQRmqsEZVscdOqblIoyV8C28j2NHJSVD4eVo7ab2JXI7BL2PaN8bcid9ycUjnPSRWuFtMe2rRe7pbkZsKFUOYRN0K4FNBCCyXn0W/NaDCxrElFRBUhli8SGtKuC666p6hJ7YSzzRLaKvs9SyKFkvzcQ6HheAk1lP1z6B9bmYbSFEVYunlmlmPn8oK6DiFTj3qQ35K7m6dMpFDOIG6EcBp3PD2UtmQnYaOJcflsJaOSj3FY08hSZ/3liWKFPhHaUHnqQ0k+E/OhmlDahpXzTexrRgIhlmGt0nPdytYaDqjX876sBSivqwolx32rPMkAUJrCyQ5i6p0jOulEKDMBSmmVmoyhTZfSyLAcdCzlCu2+vhdpAUrhmHuhMig/STcIlaaJ28iK8j9fL/66VbSDHLHO5Esb6rYWoBR+aacrg5L7wNsoVJrCYytIiopWeotml2pPCS2ppwy1VAtQChPJyQqh5H5mMpDut80JIX6DC71ZCxVNo60RDmGjKUOVawHKQrLhCA6UHtkmQyn8xPZ7/nhU9k8N7Vd5mVHo9QqdSBmqUwtQTiYzr+NAyb3TbTKagndvLsboMS2P6lclCw2DHUr+u7BMAn+ZLtKYLRqAMtoilSVSQsn9ut5kQIVnny6WM9k8sk0GWugrUaEkLFLIX6GL1OSlASiFoxF+vnIouV+ZDKqo6q2TJaeKbLseuoSTnGcV/VvhVuk36QK18RqAchfhJl1MKA0zW4nSjswF4jl539xP8ELF21AdJCx14h9FFWi9FqCsEIRIi1cDyjdqTEbWfdFDEtJ2mMYiLZmKBpWI6ukf0sQZG6EBKBFbM6WdfbhQcu9aTcbWqQr0Q12Rewz5822KRg0qbbEt5TUAJWJRSXqbDzaU3C9NRtcMZO2Ce2JH6Sn5FkcuVFZU6rEqtQAloiLCOJWg5K4bnsqU9TyB8un/URPKd7yCYmLLXwNQbvAi3RRPAOW1nYanErdilPw2FEnFouv1kXe9OKcyOx3K9cRvEQIoufcCDQ+lH8nWCcpUx3pIJF4m8aR1gAag3IcosnXUpBqU3C+gqywlgHIe1X+YeEN0ixdp8WtEDV1LhquhRO01qVYRSu6PhofSZ6GTR5UnJYaBhLvvJyAOZgja4mIoF1EMRMigvLPB8FSS5DpYJ67bZ92StRFCyYpmhQkjjFxscS2UE1DrtHJVysmg5D4LNzqUm0kScNJNEWsOymxYIxnVH0AEKIuscimUPssRjRg6SV0ouQ+MDuVFInP6WqLYK2T3Ca0nmIlBlDkMTQ53LZTIjr/MpDKUDDp+EytJrPVxRFAOXYMfeVoFRkDsU0u6G5GepocuhRJpe69rVR3KjzoYY7J3/0ihVeF3X1wR2OdQH8bbIIRZyGc0qoZQTjLi/BByKKcqYhKjaBsxlNw7I5hi0laAuXMS7uXe08mg5BvxqEw/ihvwNk64KKR/5JBJFSjn4m0ltM5C+6KDnQAlW47fnkdTuxG4r6QOnlQBOK+WIQQzTc0Yc53rkC1JVwdKvhFnritZZCMGhvuZAkoujh0mjzxJLc5gTd/U35Og5Szapl4nuxITHkSE+Vk5a2U+uiF9halUgbK3NoLcN63+tsh8641650DJnWCFyQ2Djs9sxCkmVibZg00Ro0i6cn1PI2Hnu1CyxNRoEcT3mNSDstfcfEKqcsoMsS9vzlWTk6B8YwIbTO6wt8B2VstlD4XSGYhVbMBpWSF+nm3TWYnZ8hixOgiiGWx93niRYUSwqlD2lpicL7JjM/Bl8S2UWFYnKii5d/1YYPKhoKqV78lI8cvHtI2X2NZo67y6RE/4SshC5oe5UytzJIaj1dFiY82qRCSW1pfFHPL9680qQtlr8VyQleq4Hh9VGjRc/C9qTc6DkgnHb/hTKNNDyVSk7SFp41Kpl2xRf/VnCa+YpfyyQ96ZfmRrjNRburj3hbRYlNmqwh6HLNjv+FLxeP2Fb1WF0vbF8S1feqCnvatX7YeHzfIdKXXxknBnQsn16J5Jq9gRcRFz4qrjB5FZP/rq2iDpmaDKJ5fPkbrM37fsYk9H6s6Ni23PT2b77hTboE2qvmTI6s35qdOioiNHdzdVZ1VKlTN8vPlfdShJFII5aUsL5bVknTOZWytpfQiY/uaeS0ePHi2v7Vwit/e7LmsgbMp0lR5gzJH+iFNkLkzzD4iwyK1PFls1AGXGYpNzoeTeG6tvKMtV+6yn2y0l1gxXJejRgRfdIeXRfJ/05G6EsuqIydlQ6t3xm6XWZ13i4Nxp2qI8ZoBd+eoSxUwOEO4+KEPwfXf0UHI6P0E0U5WPulE4Zdj0ltKgexxWPc8oC1c8KL1wG5RLCCp0KYDyzj59U7koR/lHXYZaBt6xTlmXskwQsUFJvMrBdhN3QTmHpMCHAih17/g9FaHwk54uUhEnaoGSbhK1MhFbRR3P3uzmHii9phAV3lUCpe4dv60FigbuU0TLBdU30waNEBkU7TtIOTp1KCHoFiinE9odFUHJ/UHnVNZPSaP+pM9KboMvnUkV9JJoJdBAqnSn1rHbdQOUdVdIt2Yrg/KjLp1TaTr+Jt0n/ZRcGbrwEi/yHkVy8X038RRohHB06nooz5IfdaoMShYcv2uXUOQiFzEW/7sIT9fzb5CpHjimwUISL+cQwk6rBpQNQfjtmEOzUUEhlNzv9H/005hMwi6oKhGz3PZrvgRRy1vlA94/g53whFYieyg1oDxl6r55D6cNlrLjVE9EKZTcNxmwZuT2VOBPD4UktuJHrq4IxevV1mM+vppVWFt5/MtEDtScLbjRg8RQ2lz6x7fKnBxYtXoZ7WtUMZQe7SYWtGNFJ07OU0f8SW9aGiMbNaGZwEmQ3rZcbrRaNEx0z1H3FouDCuig7HW0TA0S5XJhZd4k+oehGEpmHL+mHS8USn/5I2ozWyni+u1vnixhmFh3qJ20nNqmu/MyRP0Zk5eukRhSJYWn22t0Ci2Ufbe2ry2oIMGuLVWNbx7Ka1JWYVc5lNy7PiZW5Lfzwyu100OEPVHA5PKbi1PoA09YuWp1giOZXlt8g5ZtqqcKGDykeXVjnWO8gjOHW9X+TGT3ffuMSO4qzV/U1taW13NqY7AKFZ9VgJJbamJL4fH7e9qGXTkT1Kczm3fFHkmOViGsz+zUyy/EbbVF3bb59uHs+EiFX6FJXfnzN9uaWXLlYuyReKeUalTjcCc3QMmA4xfEHJTX/gueHUCpMSh17/gFMQgl1PgFKLUHpd4dvyAWobxzFR4fQKkxKLlPouH5AZQag5L7F3h+AKXWoNS94xfEIJT6d/yCmIOS+1MUPEKAUmNQsuD4BbEGJROOXxBjUDLi+AWxBCX3xiR4igClxqDk/u4DjxGg1BiU3K/gMQKUWoOSew2eI0CpNSjB8QtQag5K7r0x8CQBSo1Byf03PEmAUmtQcv8DjxKg1BqUd5rgWQKUGoOS+yQFHiZAqTEowfELUGoPSu4FeJoApdag/GgxPE6AUmNQcn8aDc8ToNQYlNzvvOGBApQag5K7BQ8UoNQalB5H4IkClBqDknvjodY/cNjpJq84AZQz9Awl9/dcLX/a3u1zAhKnAXUy2uVYJN2yW9dQatnxa43ttJ31cBp6S83JuVByMzR621G7npw0Oz4rEjAwFJTXWrV4063NdgfFr1sGG4uMBCX3rlVzt3y8zN9x6D45H0gwEJRac/x6756DPANsXjuwYBwoNeX4HfMou0EfbQn1uYwD5TXNOH6jstZJHrH5PHiTjQIl94k2stv4VVvkzkgcWtIKRBgDSk04flNn+eOc/jqyORiYMASU3B/dn9148ZiKiIsGKowA5Z3/c+ctjl3bSXTG/MxMK3DBPpTcZ+luzG6W8KQ6GFsPZDAPJfeBmxy/O7Zv4WnkOwPQYB5K7mfuuLk1szJ4Wh3LBjhYh9LD5c/YuzrMi1eiuamAB9tQcu90uza7OdnJK1XauWQAhGkouV+70PEbdSuGV0MZiVAum2koXef43bFqC6+WQqaACZhlKLlSl9xR6rkMXk2NzwoETNiF8o0ap99OUmlFKK+21i3zA1BYhdLpjt+xJ315pwhMwOxCyf3SmbcyYkUM7zQVtwMrjELJXXfajSSviuCdqjlQsotRKK9NdM5trDlaxTtbXmACZhNK7j0nOH7rh1R48a5QHZiAmYRSfcfv2LW+vMs0clU3MMMelCo7foPvxvAuVURcOFDDHJR3NqiY3WyP4F0uMAGzByX32TNqZTeXqni3CEzAzEGpjuO3fkiYF+82gQmYNShVcPyOzbvHu1erwQTMFpQeHQqzm2ExvPs19zjgwxCU3DtKdlcnbw3gNaGcWWACZghK7tfUmUJXeRWvGfmDCZghKLk4uuymtILXlkKmwHlBzEDJnaDJbm7w2hNUAmYHyjcmELa0WxPZDUpLoBIwI1By7xLZuTWT3YAJmGUoSRy/mspuwATMMJRcD+7aTQWvA0ElYCagvIYzzRe47AavD3lVgglY/1By78luXu2+G8PrR3VBYALWPZTcL+SymxBeXwITsP6h5BbpOrsBEzCTUN7ZJ5rdLOB1qpmZY4ArPUPJfYbsVyJ1k92gTcAn64EsHUPJfYBau0ngdS4wAesaSu4PDi3amRjCMyAwAesZyo+69J/dgAmYMSi5d0Y8yW5mHOMZUhqYgHULJfe7JFtTUtpu8IwJKgHrFkrum2xkN2gTMFQC1ieUT5+I3xbCMyqoBKxLKD08vp7BMywwAesOSg/ua9/mGReYgPUE5dMe3Be/zX+OZ17z2oE1fUD5tMc//kOoAYgEE7BuoOxD0ssoSIIJWA9Qejz9tS8ZCUkwAWseSlt2YzAkwQSsZSj7sps0IyJpMwGPAxOw9qDsHUp+MdSgRIIJWJNQGi27Qaooth7I0wyUHh5f+xJvdCRtJuDXAD1tQGnU7AapY2ACdj+Utuzmc4AkmIA1A6Wh1m6wTcDnwATsPighuwETsMag7Fu7gaGkiMAE7A4oIbuREZiAXQxlX3YTCtmNjMAE7EIobdkNMIehFjABuwZKyG5IVLAbWHQ6lJDdkCoMTMDOhRKyGwp5VW4EHp0F5dMez0F2Q6W6oHgg0hlQPnKmAZJ0AhOwE6D0gOxGoaASsMpQQnajhhIyrQAlZDda08HYeoBSrewGkFRLxq4EDM40jcrIJmDIbjSruRsASshutKYco1YChuxGy8rYNgmgBGea1mRIEzBkN1rX+KxIgBJ7KAnZjYsU0+YHUEJ2ozW15HsDlJDdaE0FJwBKWLvRnAxkAobsRjcyjgkYshsdySgmYMhudCVjmIAhu9GZjFAJmGTtBpDUhNg3AcMWbh2KdRMwDpKQ3WhObJuAIbvRqVg2AUN2o1uxawKG7Ea/SmPVBAxrN3oWo5WAYd+NvsWkCRiyG71r+MVII0BplIPhWRFzJmDYd8OCWj70ZhhKyG50qoJqhqD8f8r5N4AVfr8eAAAAAElFTkSuQmCC"
      />
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarTogglerDemo02"
      aria-controls="navbarTogglerDemo02"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarTogglerDemo02">
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0"></ul>
      <ul class="navbar-nav mt-2 mt-lg-0 navbar-right">
        <li class="nav-item">
          <router-link to="/" class="nav-link">{{
            $t("nav.home")
          }}</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/contactPage" class="nav-link">{{
            $t("nav.contact")
          }}</router-link>
        </li>
        <li class="nav-item dropdown" v-if="account.user">
          <a
            class="nav-link dropdown-toggle"
            href="#"
            id="navbarDropdownMenuLink"
            data-toggle="dropdown"
            aria-haspopup="true"
            aria-expanded="false"
          >
            {{ account.user.firstName }}
          </a>
          <div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
            <a class="nav-link">{{ account.user.email }}</a>
            <router-link to="/login" class="dropdown-item">{{
              $t("nav.logout")
            }}</router-link>
          </div>
        </li>
        <li class="nav-item" v-if="!account.user">
          <router-link to="/register" class="nav-link"
            ><span class="glyphicon glyphicon-user"></span>
            {{ $t("nav.register") }}</router-link
          >
        </li>
        <li class="nav-item" v-if="!account.user">
          <router-link to="/login" class="nav-link"
            ><span class="glyphicon glyphicon-log-in"></span>
            {{ $t("nav.login") }}</router-link
          >
        </li>
        <li class="nav-item">
          <LocaleSwitcher />
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import { mapState, mapActions } from "vuex";
import LocaleSwitcher from "../components/LocaleSwitcher";

export default {
  methods: {
    setLocale(locale) {
      this.$LocaleSwitcher.locale = locale;
    },
  },
  computed: {
    ...mapState({
      account: (state) => state.account,
    }),
  },
  components: { LocaleSwitcher },
};
</script>

