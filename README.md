# mysql-postgresql-usage

(C)  Federico Razzoli  2018

Collection of cheatsheets and snippets for MySQL and PostgreSQL.
This project serves as a reference for people who is only familiar with one of these systems.

## Glossary

<table>
    <tr>
        <th>MySQL</th>
        <th>PostgreSQL</th>
    </tr>
    <tr>
        <td>Dataset</td>
        <td>Cluster</td>
    </tr>
    <tr>
        <td>Optimizer</td>
        <td>Planner</td>
    </tr>
    <tr>
        <td>Master</td>
        <td>Primary</td>
    </tr>
    <tr>
        <td>Slave</td>
        <td>Standby</td>
    </tr>
    <tr>
        <td>Readonly Slave</td>
        <td>Warm Standby</td>
    </tr>
</table>

## Concepts

Some functionalities are based on different idea, so this mapping is a very loosy approximation.
Use it as a hint about what to study, don't try to use MySQL concepts in PostgreSQL (or the other way around).

<table>
    <tr>
        <th>MySQL</th>
        <th>PostgreSQL</th>
    </tr>
    <tr>
        <td>
            Binary Log<br>
            InnoDB Transaction Logs
        </td>
        <td>
            WAL
        </td>
    </tr>
    <tr>
        <td>Doublewrite Buffer</td>
        <td>Full Page Writes</td>
    </tr>
    <tr>
        <td>Row Based Replication (RBR)</td>
        <td>Streaming Replication or Logical Repliaction</td>
    </tr>
    <tr>
        <td>Database</td>
        <td>Schema</td>
    </tr>
    <tr>
        <td>/</td>
        <td>Database</td>
    </tr>
    <tr>
        <td>
            Tablespace (InnoDB)<br>
            Data File (MyISAM)
        </td>
        <td>
            Heap File
        </td>
    </tr>
</table>

# Maintainer

Federico Razzoli < federico.razzoli.dba@gmail.com >
