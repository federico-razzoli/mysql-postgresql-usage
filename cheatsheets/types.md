# Datatypes

**Work In Progress**

# Integer Types

<table>
    <tr>
        <th>MySQL</th>
        <th>PostgreSQL</th>
        <th>Size (bytes)</th>
    </tr>
    <tr>
        <td>TINYINT</td>
        <td>/</td>
        <td>1</td>
    </tr>
    <tr>
        <td>SMALLINT</td>
        <td>SMALLINT</td>
        <td>2</td>
    </tr>
    <tr>
        <td>MEDIUMINT</td>
        <td>/</td>
        <td>3 on disk, 4 in memory</td>
    </tr>
    <tr>
        <td>INT / INTEGER</td>
        <td>INTEGER</td>
        <td>4</td>
    </tr>
    <tr>
        <td>BIGINT</td>
        <td>BIGINT</td>
        <td>8</td>
    </tr>
</table>

Modifiers only available in MySQL:
* UNSIGNED
* ZEROFILL

# Real Types

<table>
    <tr>
        <th>MySQL</th>
        <th>Size in MySQL (digits)</th>
        <th>PostgreSQL</th>
        <th>Size in PostgreSQL (digits)</th>
    </tr>
    <tr>
        <td>FLOAT</td>
        <td>53</td>
        <td>/</td>
        <td>/</td>
    </tr>
    <tr>
        <td>REAL</td>
        <td>Synonym for FLOAT or DOUBLE (depending on SQL_MODE)</td>
        <td>REAL</td>
        <td>6 decimals</td>
    </tr>
    <tr>
        <td>DOUBLE / DOUBLE PRECISION</td>
        <td>8 bytes</td>
        <td>DOUBLE PRECISION</td>
        <td>15 decimals</td>
    </tr>
    <tr>
        <td>DECIMAL / NUMERIC</td>
        <td>?</td>
        <td>DECIMAL / NUMERIC</td>
        <td>integer part: 131072; decimal part: 16383</td>
    </tr>
</table>

Modifiers only available in MySQL:
* UNSIGNED
